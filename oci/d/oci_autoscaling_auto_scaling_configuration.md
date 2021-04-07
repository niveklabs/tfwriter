# oci_autoscaling_auto_scaling_configuration

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
module "oci_autoscaling_auto_scaling_configuration" {
  source = "./modules/oci/d/oci_autoscaling_auto_scaling_configuration"

  # auto_scaling_configuration_id - (required) is a type of string
  auto_scaling_configuration_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_scaling_configuration_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_autoscaling_auto_scaling_configuration" "this" {
  # auto_scaling_configuration_id - (required) is a type of string
  auto_scaling_configuration_id = var.auto_scaling_configuration_id
}
```

[top](#index)

### Outputs

```terraform
output "auto_scaling_resources" {
  description = "returns a list of object"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.auto_scaling_resources
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.compartment_id
}

output "cool_down_in_seconds" {
  description = "returns a number"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.cool_down_in_seconds
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.is_enabled
}

output "max_resource_count" {
  description = "returns a number"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.max_resource_count
}

output "min_resource_count" {
  description = "returns a number"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.min_resource_count
}

output "policies" {
  description = "returns a list of object"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.policies
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_autoscaling_auto_scaling_configuration.this.time_created
}

output "this" {
  value = oci_autoscaling_auto_scaling_configuration.this
}
```

[top](#index)