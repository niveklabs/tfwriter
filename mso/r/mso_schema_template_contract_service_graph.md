# mso_schema_template_contract_service_graph

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
module "mso_schema_template_contract_service_graph" {
  source = "./modules/mso/r/mso_schema_template_contract_service_graph"

  # contract_name - (required) is a type of string
  contract_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # service_graph_name - (required) is a type of string
  service_graph_name = null
  # service_graph_schema_id - (optional) is a type of string
  service_graph_schema_id = null
  # service_graph_site_id - (optional) is a type of string
  service_graph_site_id = null
  # service_graph_template_name - (optional) is a type of string
  service_graph_template_name = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null

  node_relationship = [{
    consumer_connector_bd_name                = null
    consumer_connector_bd_schema_id           = null
    consumer_connector_bd_template_name       = null
    consumer_connector_cluster_interface      = null
    consumer_connector_redirect_policy        = null
    consumer_connector_redirect_policy_tenant = null
    consumer_subnet_ips                       = []
    provider_connector_bd_name                = null
    provider_connector_bd_schema_id           = null
    provider_connector_bd_template_name       = null
    provider_connector_cluster_interface      = null
    provider_connector_redirect_policy        = null
    provider_connector_redirect_policy_tenant = null
    provider_subnet_ips                       = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "contract_name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "service_graph_name" {
  description = "(required)"
  type        = string
}

variable "service_graph_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_graph_site_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_graph_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "site_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "node_relationship" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      consumer_connector_bd_name                = string
      consumer_connector_bd_schema_id           = string
      consumer_connector_bd_template_name       = string
      consumer_connector_cluster_interface      = string
      consumer_connector_redirect_policy        = string
      consumer_connector_redirect_policy_tenant = string
      consumer_subnet_ips                       = list(string)
      provider_connector_bd_name                = string
      provider_connector_bd_schema_id           = string
      provider_connector_bd_template_name       = string
      provider_connector_cluster_interface      = string
      provider_connector_redirect_policy        = string
      provider_connector_redirect_policy_tenant = string
      provider_subnet_ips                       = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_contract_service_graph" "this" {
  contract_name               = var.contract_name
  schema_id                   = var.schema_id
  service_graph_name          = var.service_graph_name
  service_graph_schema_id     = var.service_graph_schema_id
  service_graph_site_id       = var.service_graph_site_id
  service_graph_template_name = var.service_graph_template_name
  site_id                     = var.site_id
  template_name               = var.template_name

  dynamic "node_relationship" {
    for_each = var.node_relationship
    content {
      consumer_connector_bd_name                = node_relationship.value["consumer_connector_bd_name"]
      consumer_connector_bd_schema_id           = node_relationship.value["consumer_connector_bd_schema_id"]
      consumer_connector_bd_template_name       = node_relationship.value["consumer_connector_bd_template_name"]
      consumer_connector_cluster_interface      = node_relationship.value["consumer_connector_cluster_interface"]
      consumer_connector_redirect_policy        = node_relationship.value["consumer_connector_redirect_policy"]
      consumer_connector_redirect_policy_tenant = node_relationship.value["consumer_connector_redirect_policy_tenant"]
      consumer_subnet_ips                       = node_relationship.value["consumer_subnet_ips"]
      provider_connector_bd_name                = node_relationship.value["provider_connector_bd_name"]
      provider_connector_bd_schema_id           = node_relationship.value["provider_connector_bd_schema_id"]
      provider_connector_bd_template_name       = node_relationship.value["provider_connector_bd_template_name"]
      provider_connector_cluster_interface      = node_relationship.value["provider_connector_cluster_interface"]
      provider_connector_redirect_policy        = node_relationship.value["provider_connector_redirect_policy"]
      provider_connector_redirect_policy_tenant = node_relationship.value["provider_connector_redirect_policy_tenant"]
      provider_subnet_ips                       = node_relationship.value["provider_subnet_ips"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_template_contract_service_graph.this.id
}

output "this" {
  value = mso_schema_template_contract_service_graph.this
}
```

[top](#index)