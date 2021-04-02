# oci_log_analytics_log_analytics_entity

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_log_analytics_log_analytics_entity" {
  source = "./modules/oci/r/oci_log_analytics_log_analytics_entity"

  # cloud_resource_id - (optional) is a type of string
  cloud_resource_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # entity_type_name - (required) is a type of string
  entity_type_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hostname - (optional) is a type of string
  hostname = null
  # management_agent_id - (optional) is a type of string
  management_agent_id = null
  # name - (required) is a type of string
  name = null
  # namespace - (required) is a type of string
  namespace = null
  # properties - (optional) is a type of map of string
  properties = {}
  # source_id - (optional) is a type of string
  source_id = null
  # timezone_region - (optional) is a type of string
  timezone_region = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "entity_type_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_agent_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "source_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_log_analytics_log_analytics_entity" "this" {
  cloud_resource_id   = var.cloud_resource_id
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  entity_type_name    = var.entity_type_name
  freeform_tags       = var.freeform_tags
  hostname            = var.hostname
  management_agent_id = var.management_agent_id
  name                = var.name
  namespace           = var.namespace
  properties          = var.properties
  source_id           = var.source_id
  timezone_region     = var.timezone_region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "are_logs_collected" {
  description = "returns a bool"
  value       = oci_log_analytics_log_analytics_entity.this.are_logs_collected
}

output "cloud_resource_id" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.cloud_resource_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_log_analytics_log_analytics_entity.this.defined_tags
}

output "entity_type_internal_name" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.entity_type_internal_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_log_analytics_log_analytics_entity.this.freeform_tags
}

output "hostname" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.hostname
}

output "id" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.lifecycle_details
}

output "management_agent_compartment_id" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.management_agent_compartment_id
}

output "management_agent_display_name" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.management_agent_display_name
}

output "management_agent_id" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.management_agent_id
}

output "properties" {
  description = "returns a map of string"
  value       = oci_log_analytics_log_analytics_entity.this.properties
}

output "source_id" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.source_id
}

output "state" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.time_updated
}

output "timezone_region" {
  description = "returns a string"
  value       = oci_log_analytics_log_analytics_entity.this.timezone_region
}

output "this" {
  value = oci_log_analytics_log_analytics_entity.this
}
```

[top](#index)