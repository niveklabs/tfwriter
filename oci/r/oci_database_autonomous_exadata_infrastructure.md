# oci_database_autonomous_exadata_infrastructure

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
module "oci_database_autonomous_exadata_infrastructure" {
  source = "./modules/oci/r/oci_database_autonomous_exadata_infrastructure"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # license_model - (optional) is a type of string
  license_model = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # shape - (required) is a type of string
  shape = null
  # subnet_id - (required) is a type of string
  subnet_id = null

  maintenance_window_details = [{
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

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "maintenance_window_details" {
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
resource "oci_database_autonomous_exadata_infrastructure" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  domain              = var.domain
  freeform_tags       = var.freeform_tags
  license_model       = var.license_model
  nsg_ids             = var.nsg_ids
  shape               = var.shape
  subnet_id           = var.subnet_id

  dynamic "maintenance_window_details" {
    for_each = var.maintenance_window_details
    content {
      hours_of_day       = maintenance_window_details.value["hours_of_day"]
      lead_time_in_weeks = maintenance_window_details.value["lead_time_in_weeks"]
      preference         = maintenance_window_details.value["preference"]
      weeks_of_month     = maintenance_window_details.value["weeks_of_month"]

      dynamic "days_of_week" {
        for_each = maintenance_window_details.value.days_of_week
        content {
          name = days_of_week.value["name"]
        }
      }

      dynamic "months" {
        for_each = maintenance_window_details.value.months
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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_exadata_infrastructure.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_exadata_infrastructure.this.freeform_tags
}

output "hostname" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.hostname
}

output "id" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.last_maintenance_run_id
}

output "license_model" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.lifecycle_details
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = oci_database_autonomous_exadata_infrastructure.this.maintenance_window
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.next_maintenance_run_id
}

output "scan_dns_name" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.scan_dns_name
}

output "state" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.time_created
}

output "zone_id" {
  description = "returns a string"
  value       = oci_database_autonomous_exadata_infrastructure.this.zone_id
}

output "this" {
  value = oci_database_autonomous_exadata_infrastructure.this
}
```

[top](#index)