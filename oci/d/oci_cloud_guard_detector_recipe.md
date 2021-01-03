# oci_cloud_guard_detector_recipe

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_cloud_guard_detector_recipe" {
  source = "./modules/oci/d/oci_cloud_guard_detector_recipe"

  # detector_recipe_id - (required) is a type of string
  detector_recipe_id = null
}
```

[top](#index)

### Variables

```terraform
variable "detector_recipe_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_cloud_guard_detector_recipe" "this" {
  detector_recipe_id = var.detector_recipe_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_detector_recipe.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.description
}

output "detector" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.detector
}

output "detector_rules" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_detector_recipe.this.detector_rules
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.display_name
}

output "effective_detector_rules" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_detector_recipe.this.effective_detector_rules
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_detector_recipe.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.id
}

output "owner" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.owner
}

output "source_detector_recipe_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.source_detector_recipe_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_detector_recipe.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_cloud_guard_detector_recipe.this.time_updated
}

output "this" {
  value = oci_cloud_guard_detector_recipe.this
}
```

[top](#index)