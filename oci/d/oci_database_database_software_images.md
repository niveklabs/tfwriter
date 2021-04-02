# oci_database_database_software_images

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
module "oci_database_database_software_images" {
  source = "./modules/oci/d/oci_database_database_software_images"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # image_shape_family - (optional) is a type of string
  image_shape_family = null
  # image_type - (optional) is a type of string
  image_type = null
  # is_upgrade_supported - (optional) is a type of bool
  is_upgrade_supported = null
  # state - (optional) is a type of string
  state = null

  filter = [{
    name   = null
    regex  = null
    values = []
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

variable "display_name" {
  description = "(optional)"
  type        = string
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

variable "is_upgrade_supported" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_database_software_images" "this" {
  compartment_id       = var.compartment_id
  display_name         = var.display_name
  image_shape_family   = var.image_shape_family
  image_type           = var.image_type
  is_upgrade_supported = var.is_upgrade_supported
  state                = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "database_software_images" {
  description = "returns a list of object"
  value       = data.oci_database_database_software_images.this.database_software_images
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_database_software_images.this.id
}

output "this" {
  value = oci_database_database_software_images.this
}
```

[top](#index)