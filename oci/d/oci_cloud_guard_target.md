# oci_cloud_guard_target

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
module "oci_cloud_guard_target" {
  source = "./modules/oci/d/oci_cloud_guard_target"

  # target_id - (required) is a type of string
  target_id = null
}
```

[top](#index)

### Variables

```terraform
variable "target_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_cloud_guard_target" "this" {
  target_id = var.target_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_target.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_target.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.id
}

output "inherited_by_compartments" {
  description = "returns a list of string"
  value       = data.oci_cloud_guard_target.this.inherited_by_compartments
}

output "lifecyle_details" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.lifecyle_details
}

output "recipe_count" {
  description = "returns a number"
  value       = data.oci_cloud_guard_target.this.recipe_count
}

output "state" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_target.this.system_tags
}

output "target_detector_recipes" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_target.this.target_detector_recipes
}

output "target_resource_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.target_resource_id
}

output "target_resource_type" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.target_resource_type
}

output "target_responder_recipes" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_target.this.target_responder_recipes
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_cloud_guard_target.this.time_updated
}

output "this" {
  value = oci_cloud_guard_target.this
}
```

[top](#index)