# mso_schema_template_service_graph

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_service_graph" {
  source = "./modules/mso/d/mso_schema_template_service_graph"

  # node_index - (required) is a type of number
  node_index = null
  # schema_id - (required) is a type of string
  schema_id = null
  # service_graph_name - (required) is a type of string
  service_graph_name = null
  # service_node_type - (optional) is a type of string
  service_node_type = null
  # template_name - (required) is a type of string
  template_name = null

  site_nodes = [{
    node_name   = null
    site_id     = null
    tenant_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "node_index" {
  description = "(required)"
  type        = number
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "service_graph_name" {
  description = "(required)"
  type        = string
}

variable "service_node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "site_nodes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      node_name   = string
      site_id     = string
      tenant_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_service_graph" "this" {
  node_index         = var.node_index
  schema_id          = var.schema_id
  service_graph_name = var.service_graph_name
  service_node_type  = var.service_node_type
  template_name      = var.template_name

  dynamic "site_nodes" {
    for_each = var.site_nodes
    content {
      node_name   = site_nodes.value["node_name"]
      site_id     = site_nodes.value["site_id"]
      tenant_name = site_nodes.value["tenant_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_service_graph.this.id
}

output "service_node_type" {
  description = "returns a string"
  value       = data.mso_schema_template_service_graph.this.service_node_type
}

output "this" {
  value = mso_schema_template_service_graph.this
}
```

[top](#index)