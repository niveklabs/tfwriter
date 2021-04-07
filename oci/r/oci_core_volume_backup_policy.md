# oci_core_volume_backup_policy

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
module "oci_core_volume_backup_policy" {
  source = "./modules/oci/r/oci_core_volume_backup_policy"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # destination_region - (optional) is a type of string
  destination_region = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

  schedules = [{
    backup_type       = null
    day_of_month      = null
    day_of_week       = null
    hour_of_day       = null
    month             = null
    offset_seconds    = null
    offset_type       = null
    period            = null
    retention_seconds = null
    time_zone         = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "destination_region" {
  description = "(optional)"
  type        = string
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

variable "schedules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      backup_type       = string
      day_of_month      = number
      day_of_week       = string
      hour_of_day       = number
      month             = string
      offset_seconds    = number
      offset_type       = string
      period            = string
      retention_seconds = number
      time_zone         = string
    }
  ))
  default = []
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
resource "oci_core_volume_backup_policy" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # destination_region - (optional) is a type of string
  destination_region = var.destination_region
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags

  dynamic "schedules" {
    for_each = var.schedules
    content {
      # backup_type - (required) is a type of string
      backup_type = schedules.value["backup_type"]
      # day_of_month - (optional) is a type of number
      day_of_month = schedules.value["day_of_month"]
      # day_of_week - (optional) is a type of string
      day_of_week = schedules.value["day_of_week"]
      # hour_of_day - (optional) is a type of number
      hour_of_day = schedules.value["hour_of_day"]
      # month - (optional) is a type of string
      month = schedules.value["month"]
      # offset_seconds - (optional) is a type of number
      offset_seconds = schedules.value["offset_seconds"]
      # offset_type - (optional) is a type of string
      offset_type = schedules.value["offset_type"]
      # period - (required) is a type of string
      period = schedules.value["period"]
      # retention_seconds - (required) is a type of number
      retention_seconds = schedules.value["retention_seconds"]
      # time_zone - (optional) is a type of string
      time_zone = schedules.value["time_zone"]
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
  value       = oci_core_volume_backup_policy.this.defined_tags
}

output "destination_region" {
  description = "returns a string"
  value       = oci_core_volume_backup_policy.this.destination_region
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_volume_backup_policy.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_volume_backup_policy.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_volume_backup_policy.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_volume_backup_policy.this.time_created
}

output "this" {
  value = oci_core_volume_backup_policy.this
}
```

[top](#index)