# oci_log_analytics_log_analytics_entities

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_log_analytics_log_analytics_entities" {
  source = "./modules/oci/d/oci_log_analytics_log_analytics_entities"

  # cloud_resource_id - (optional) is a type of string
  cloud_resource_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # entity_type_name - (optional) is a type of list of string
  entity_type_name = []
  # hostname - (optional) is a type of string
  hostname = null
  # hostname_contains - (optional) is a type of string
  hostname_contains = null
  # is_management_agent_id_null - (optional) is a type of string
  is_management_agent_id_null = null
  # lifecycle_details_contains - (optional) is a type of string
  lifecycle_details_contains = null
  # name - (optional) is a type of string
  name = null
  # name_contains - (optional) is a type of string
  name_contains = null
  # namespace - (required) is a type of string
  namespace = null
  # source_id - (optional) is a type of string
  source_id = null
  # state - (optional) is a type of string
  state = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "entity_type_name" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_management_agent_id_null" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lifecycle_details_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "source_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_log_analytics_log_analytics_entities" "this" {
  cloud_resource_id           = var.cloud_resource_id
  compartment_id              = var.compartment_id
  entity_type_name            = var.entity_type_name
  hostname                    = var.hostname
  hostname_contains           = var.hostname_contains
  is_management_agent_id_null = var.is_management_agent_id_null
  lifecycle_details_contains  = var.lifecycle_details_contains
  name                        = var.name
  name_contains               = var.name_contains
  namespace                   = var.namespace
  source_id                   = var.source_id
  state                       = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entities.this.id
}

output "log_analytics_entity_collection" {
  description = "returns a list of object"
  value       = data.oci_log_analytics_log_analytics_entities.this.log_analytics_entity_collection
}

output "this" {
  value = oci_log_analytics_log_analytics_entities.this
}
```

[top](#index)