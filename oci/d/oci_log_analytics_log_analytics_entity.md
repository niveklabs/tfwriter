# oci_log_analytics_log_analytics_entity

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
module "oci_log_analytics_log_analytics_entity" {
  source = "./modules/oci/d/oci_log_analytics_log_analytics_entity"

  # log_analytics_entity_id - (required) is a type of string
  log_analytics_entity_id = null
  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "log_analytics_entity_id" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_log_analytics_log_analytics_entity" "this" {
  log_analytics_entity_id = var.log_analytics_entity_id
  namespace               = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "are_logs_collected" {
  description = "returns a bool"
  value       = data.oci_log_analytics_log_analytics_entity.this.are_logs_collected
}

output "cloud_resource_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.cloud_resource_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_log_analytics_log_analytics_entity.this.defined_tags
}

output "entity_type_internal_name" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.entity_type_internal_name
}

output "entity_type_name" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.entity_type_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_log_analytics_log_analytics_entity.this.freeform_tags
}

output "hostname" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.lifecycle_details
}

output "management_agent_compartment_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.management_agent_compartment_id
}

output "management_agent_display_name" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.management_agent_display_name
}

output "management_agent_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.management_agent_id
}

output "name" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.name
}

output "properties" {
  description = "returns a map of string"
  value       = data.oci_log_analytics_log_analytics_entity.this.properties
}

output "source_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.source_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.time_updated
}

output "timezone_region" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entity.this.timezone_region
}

output "this" {
  value = oci_log_analytics_log_analytics_entity.this
}
```

[top](#index)