# oci_database_cloud_exadata_infrastructure

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
module "oci_database_cloud_exadata_infrastructure" {
  source = "./modules/oci/r/oci_database_cloud_exadata_infrastructure"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # compute_count - (optional) is a type of number
  compute_count = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # shape - (required) is a type of string
  shape = null
  # storage_count - (optional) is a type of number
  storage_count = null

  maintenance_window = [{
    days_of_week = [{
      name = null
    }]
    hours_of_day       = []
    lead_time_in_weeks = null
    months = [{
      name = null
    }]
    preference     = null
    weeks_of_month = []
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

variable "compute_count" {
  description = "(optional)"
  type        = number
  default     = null
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

variable "shape" {
  description = "(required)"
  type        = string
}

variable "storage_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maintenance_window" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      days_of_week = list(object(
        {
          name = string
        }
      ))
      hours_of_day       = list(number)
      lead_time_in_weeks = number
      months = list(object(
        {
          name = string
        }
      ))
      preference     = string
      weeks_of_month = list(number)
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
resource "oci_database_cloud_exadata_infrastructure" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  compute_count       = var.compute_count
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  shape               = var.shape
  storage_count       = var.storage_count

  dynamic "maintenance_window" {
    for_each = var.maintenance_window
    content {
      hours_of_day       = maintenance_window.value["hours_of_day"]
      lead_time_in_weeks = maintenance_window.value["lead_time_in_weeks"]
      preference         = maintenance_window.value["preference"]
      weeks_of_month     = maintenance_window.value["weeks_of_month"]

      dynamic "days_of_week" {
        for_each = maintenance_window.value.days_of_week
        content {
          name = days_of_week.value["name"]
        }
      }

      dynamic "months" {
        for_each = maintenance_window.value.months
        content {
          name = months.value["name"]
        }
      }

    }
  }

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
output "available_storage_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_cloud_exadata_infrastructure.this.available_storage_size_in_gbs
}

output "compute_count" {
  description = "returns a number"
  value       = oci_database_cloud_exadata_infrastructure.this.compute_count
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_cloud_exadata_infrastructure.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_cloud_exadata_infrastructure.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_cloud_exadata_infrastructure.this.id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_cloud_exadata_infrastructure.this.last_maintenance_run_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_cloud_exadata_infrastructure.this.lifecycle_details
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_cloud_exadata_infrastructure.this.next_maintenance_run_id
}

output "state" {
  description = "returns a string"
  value       = oci_database_cloud_exadata_infrastructure.this.state
}

output "storage_count" {
  description = "returns a number"
  value       = oci_database_cloud_exadata_infrastructure.this.storage_count
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_cloud_exadata_infrastructure.this.time_created
}

output "total_storage_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_cloud_exadata_infrastructure.this.total_storage_size_in_gbs
}

output "this" {
  value = oci_database_cloud_exadata_infrastructure.this
}
```

[top](#index)