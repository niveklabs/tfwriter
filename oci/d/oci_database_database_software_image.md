# oci_database_database_software_image

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
module "oci_database_database_software_image" {
  source = "./modules/oci/d/oci_database_database_software_image"

  # database_software_image_id - (required) is a type of string
  database_software_image_id = null
}
```

[top](#index)

### Variables

```terraform
variable "database_software_image_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_database_software_image" "this" {
  # database_software_image_id - (required) is a type of string
  database_software_image_id = var.database_software_image_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.compartment_id
}

output "database_software_image_included_patches" {
  description = "returns a list of string"
  value       = data.oci_database_database_software_image.this.database_software_image_included_patches
}

output "database_software_image_one_off_patches" {
  description = "returns a list of string"
  value       = data.oci_database_database_software_image.this.database_software_image_one_off_patches
}

output "database_version" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.database_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_database_software_image.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_database_software_image.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.id
}

output "image_shape_family" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.image_shape_family
}

output "image_type" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.image_type
}

output "included_patches_summary" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.included_patches_summary
}

output "is_upgrade_supported" {
  description = "returns a bool"
  value       = data.oci_database_database_software_image.this.is_upgrade_supported
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.lifecycle_details
}

output "ls_inventory" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.ls_inventory
}

output "patch_set" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.patch_set
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_database_software_image.this.time_created
}

output "this" {
  value = oci_database_database_software_image.this
}
```

[top](#index)