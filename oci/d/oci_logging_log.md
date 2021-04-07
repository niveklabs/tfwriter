# oci_logging_log

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_logging_log" {
  source = "./modules/oci/d/oci_logging_log"

  # log_group_id - (required) is a type of string
  log_group_id = null
  # log_id - (required) is a type of string
  log_id = null
}
```

[top](#index)

### Variables

```terraform
variable "log_group_id" {
  description = "(required)"
  type        = string
}

variable "log_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_logging_log" "this" {
  # log_group_id - (required) is a type of string
  log_group_id = var.log_group_id
  # log_id - (required) is a type of string
  log_id = var.log_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_logging_log.this.compartment_id
}

output "configuration" {
  description = "returns a list of object"
  value       = data.oci_logging_log.this.configuration
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_log.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_logging_log.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_log.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_logging_log.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_logging_log.this.is_enabled
}

output "log_type" {
  description = "returns a string"
  value       = data.oci_logging_log.this.log_type
}

output "retention_duration" {
  description = "returns a number"
  value       = data.oci_logging_log.this.retention_duration
}

output "state" {
  description = "returns a string"
  value       = data.oci_logging_log.this.state
}

output "tenancy_id" {
  description = "returns a string"
  value       = data.oci_logging_log.this.tenancy_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_logging_log.this.time_created
}

output "time_last_modified" {
  description = "returns a string"
  value       = data.oci_logging_log.this.time_last_modified
}

output "this" {
  value = oci_logging_log.this
}
```

[top](#index)