# oci_core_cross_connect

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
module "oci_core_cross_connect" {
  source = "./modules/oci/r/oci_core_cross_connect"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cross_connect_group_id - (optional) is a type of string
  cross_connect_group_id = null
  # customer_reference_name - (optional) is a type of string
  customer_reference_name = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # far_cross_connect_or_cross_connect_group_id - (optional) is a type of string
  far_cross_connect_or_cross_connect_group_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_active - (optional) is a type of bool
  is_active = null
  # location_name - (required) is a type of string
  location_name = null
  # near_cross_connect_or_cross_connect_group_id - (optional) is a type of string
  near_cross_connect_or_cross_connect_group_id = null
  # port_speed_shape_name - (required) is a type of string
  port_speed_shape_name = null

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

variable "cross_connect_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customer_reference_name" {
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

variable "far_cross_connect_or_cross_connect_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location_name" {
  description = "(required)"
  type        = string
}

variable "near_cross_connect_or_cross_connect_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_speed_shape_name" {
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
resource "oci_core_cross_connect" "this" {
  compartment_id                               = var.compartment_id
  cross_connect_group_id                       = var.cross_connect_group_id
  customer_reference_name                      = var.customer_reference_name
  defined_tags                                 = var.defined_tags
  display_name                                 = var.display_name
  far_cross_connect_or_cross_connect_group_id  = var.far_cross_connect_or_cross_connect_group_id
  freeform_tags                                = var.freeform_tags
  is_active                                    = var.is_active
  location_name                                = var.location_name
  near_cross_connect_or_cross_connect_group_id = var.near_cross_connect_or_cross_connect_group_id
  port_speed_shape_name                        = var.port_speed_shape_name

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
output "cross_connect_group_id" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.cross_connect_group_id
}

output "customer_reference_name" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.customer_reference_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_cross_connect.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.display_name
}

output "far_cross_connect_or_cross_connect_group_id" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.far_cross_connect_or_cross_connect_group_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_cross_connect.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.id
}

output "near_cross_connect_or_cross_connect_group_id" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.near_cross_connect_or_cross_connect_group_id
}

output "port_name" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.port_name
}

output "state" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_cross_connect.this.time_created
}

output "this" {
  value = oci_core_cross_connect.this
}
```

[top](#index)