# oci_log_analytics_log_analytics_log_group

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
module "oci_log_analytics_log_analytics_log_group" {
  source = "./modules/oci/d/oci_log_analytics_log_analytics_log_group"

  # log_analytics_log_group_id - (required) is a type of string
  log_analytics_log_group_id = null
  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "log_analytics_log_group_id" {
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
data "oci_log_analytics_log_analytics_log_group" "this" {
  # log_analytics_log_group_id - (required) is a type of string
  log_analytics_log_group_id = var.log_analytics_log_group_id
  # namespace - (required) is a type of string
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_group.this.time_updated
}

output "this" {
  value = oci_log_analytics_log_analytics_log_group.this
}
```

[top](#index)