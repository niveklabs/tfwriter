# oci_core_images

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
module "oci_core_images" {
  source = "./modules/oci/d/oci_core_images"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # operating_system - (optional) is a type of string
  operating_system = null
  # operating_system_version - (optional) is a type of string
  operating_system_version = null
  # shape - (optional) is a type of string
  shape = null
  # sort_by - (optional) is a type of string
  sort_by = null
  # sort_order - (optional) is a type of string
  sort_order = null
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

variable "operating_system" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operating_system_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shape" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_order" {
  description = "(optional)"
  type        = string
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
data "oci_core_images" "this" {
  compartment_id           = var.compartment_id
  display_name             = var.display_name
  operating_system         = var.operating_system
  operating_system_version = var.operating_system_version
  shape                    = var.shape
  sort_by                  = var.sort_by
  sort_order               = var.sort_order
  state                    = var.state

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
output "id" {
  description = "returns a string"
  value       = data.oci_core_images.this.id
}

output "images" {
  description = "returns a list of object"
  value       = data.oci_core_images.this.images
}

output "this" {
  value = oci_core_images.this
}
```

[top](#index)