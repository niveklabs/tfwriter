# oci_core_compute_image_capability_schema

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_compute_image_capability_schema" {
  source = "./modules/oci/r/oci_core_compute_image_capability_schema"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compute_global_image_capability_schema_version_name - (required) is a type of string
  compute_global_image_capability_schema_version_name = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # image_id - (required) is a type of string
  image_id = null
  # schema_data - (required) is a type of map of string
  schema_data = {}

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

variable "compute_global_image_capability_schema_version_name" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "image_id" {
  description = "(required)"
  type        = string
}

variable "schema_data" {
  description = "(required)"
  type        = map(string)
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
resource "oci_core_compute_image_capability_schema" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compute_global_image_capability_schema_version_name - (required) is a type of string
  compute_global_image_capability_schema_version_name = var.compute_global_image_capability_schema_version_name
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # image_id - (required) is a type of string
  image_id = var.image_id
  # schema_data - (required) is a type of map of string
  schema_data = var.schema_data

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compute_global_image_capability_schema_id" {
  description = "returns a string"
  value       = oci_core_compute_image_capability_schema.this.compute_global_image_capability_schema_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_compute_image_capability_schema.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_compute_image_capability_schema.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_compute_image_capability_schema.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_compute_image_capability_schema.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_compute_image_capability_schema.this.time_created
}

output "this" {
  value = oci_core_compute_image_capability_schema.this
}
```

[top](#index)