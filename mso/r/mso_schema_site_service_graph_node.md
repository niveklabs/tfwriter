# mso_schema_site_service_graph_node

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "mso_schema_site_service_graph_node" {
  source = "./modules/mso/r/mso_schema_site_service_graph_node"

  # schema_id - (required) is a type of string
  schema_id = null
  # service_graph_name - (required) is a type of string
  service_graph_name = null
  # service_node_type - (required) is a type of string
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
variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "service_graph_name" {
  description = "(required)"
  type        = string
}

variable "service_node_type" {
  description = "(required)"
  type        = string
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

### Resource

```terraform
resource "mso_schema_site_service_graph_node" "this" {
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
  value       = mso_schema_site_service_graph_node.this.id
}

output "this" {
  value = mso_schema_site_service_graph_node.this
}
```

[top](#index)