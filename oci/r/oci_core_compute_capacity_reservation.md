# oci_core_compute_capacity_reservation

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
module "oci_core_compute_capacity_reservation" {
  source = "./modules/oci/r/oci_core_compute_capacity_reservation"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_default_reservation - (optional) is a type of bool
  is_default_reservation = null

  instance_reservation_configs = [{
    fault_domain   = null
    instance_shape = null
    instance_shape_config = [{
      memory_in_gbs = null
      ocpus         = null
    }]
    reserved_count = null
    used_count     = null
  }]

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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
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

variable "is_default_reservation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_reservation_configs" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      fault_domain   = string
      instance_shape = string
      instance_shape_config = list(object(
        {
          memory_in_gbs = number
          ocpus         = number
        }
      ))
      reserved_count = string
      used_count     = string
    }
  ))
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
resource "oci_core_compute_capacity_reservation" "this" {
  # availability_domain - (required) is a type of string
  availability_domain = var.availability_domain
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # is_default_reservation - (optional) is a type of bool
  is_default_reservation = var.is_default_reservation

  dynamic "instance_reservation_configs" {
    for_each = var.instance_reservation_configs
    content {
      # fault_domain - (optional) is a type of string
      fault_domain = instance_reservation_configs.value["fault_domain"]
      # instance_shape - (required) is a type of string
      instance_shape = instance_reservation_configs.value["instance_shape"]
      # reserved_count - (required) is a type of string
      reserved_count = instance_reservation_configs.value["reserved_count"]

      dynamic "instance_shape_config" {
        for_each = instance_reservation_configs.value.instance_shape_config
        content {
          # memory_in_gbs - (optional) is a type of number
          memory_in_gbs = instance_shape_config.value["memory_in_gbs"]
          # ocpus - (optional) is a type of number
          ocpus = instance_shape_config.value["ocpus"]
        }
      }

    }
  }

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_compute_capacity_reservation.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_compute_capacity_reservation.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.id
}

output "is_default_reservation" {
  description = "returns a bool"
  value       = oci_core_compute_capacity_reservation.this.is_default_reservation
}

output "reserved_instance_count" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.reserved_instance_count
}

output "state" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.time_updated
}

output "used_instance_count" {
  description = "returns a string"
  value       = oci_core_compute_capacity_reservation.this.used_instance_count
}

output "this" {
  value = oci_core_compute_capacity_reservation.this
}
```

[top](#index)