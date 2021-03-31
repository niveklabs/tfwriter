# oci_database_database_software_image

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_database_software_image" {
  source = "./modules/oci/r/oci_database_database_software_image"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # database_software_image_one_off_patches - (optional) is a type of list of string
  database_software_image_one_off_patches = []
  # database_version - (required) is a type of string
  database_version = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # image_shape_family - (optional) is a type of string
  image_shape_family = null
  # image_type - (optional) is a type of string
  image_type = null
  # ls_inventory - (optional) is a type of string
  ls_inventory = null
  # patch_set - (required) is a type of string
  patch_set = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "database_software_image_one_off_patches" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "database_version" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "image_shape_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ls_inventory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "patch_set" {
  description = "(required)"
  type        = string
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
resource "oci_database_database_software_image" "this" {
  compartment_id                          = var.compartment_id
  database_software_image_one_off_patches = var.database_software_image_one_off_patches
  database_version                        = var.database_version
  defined_tags                            = var.defined_tags
  display_name                            = var.display_name
  freeform_tags                           = var.freeform_tags
  image_shape_family                      = var.image_shape_family
  image_type                              = var.image_type
  ls_inventory                            = var.ls_inventory
  patch_set                               = var.patch_set

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
output "database_software_image_included_patches" {
  description = "returns a list of string"
  value       = oci_database_database_software_image.this.database_software_image_included_patches
}

output "database_software_image_one_off_patches" {
  description = "returns a list of string"
  value       = oci_database_database_software_image.this.database_software_image_one_off_patches
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_database_software_image.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_database_software_image.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.id
}

output "image_shape_family" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.image_shape_family
}

output "image_type" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.image_type
}

output "included_patches_summary" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.included_patches_summary
}

output "is_upgrade_supported" {
  description = "returns a bool"
  value       = oci_database_database_software_image.this.is_upgrade_supported
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.lifecycle_details
}

output "ls_inventory" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.ls_inventory
}

output "state" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_database_software_image.this.time_created
}

output "this" {
  value = oci_database_database_software_image.this
}
```

[top](#index)