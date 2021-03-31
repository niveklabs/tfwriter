# oci_logging_log_group

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_logging_log_group" {
  source = "./modules/oci/d/oci_logging_log_group"

  # log_group_id - (required) is a type of string
  log_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "log_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_logging_log_group" "this" {
  log_group_id = var.log_group_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_log_group.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_log_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.time_created
}

output "time_last_modified" {
  description = "returns a string"
  value       = data.oci_logging_log_group.this.time_last_modified
}

output "this" {
  value = oci_logging_log_group.this
}
```

[top](#index)