# oci_core_cpe

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_cpe" {
  source = "./modules/oci/r/oci_core_cpe"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpe_device_shape_id - (optional) is a type of string
  cpe_device_shape_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # ip_address - (required) is a type of string
  ip_address = null

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

variable "cpe_device_shape_id" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "ip_address" {
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
resource "oci_core_cpe" "this" {
  compartment_id      = var.compartment_id
  cpe_device_shape_id = var.cpe_device_shape_id
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  ip_address          = var.ip_address

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
output "cpe_device_shape_id" {
  description = "returns a string"
  value       = oci_core_cpe.this.cpe_device_shape_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_cpe.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_cpe.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_cpe.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_cpe.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_cpe.this.time_created
}

output "this" {
  value = oci_core_cpe.this
}
```

[top](#index)