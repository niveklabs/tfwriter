# oci_database_exadata_infrastructure

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
module "oci_database_exadata_infrastructure" {
  source = "./modules/oci/r/oci_database_exadata_infrastructure"

  # activation_file - (optional) is a type of string
  activation_file = null
  # admin_network_cidr - (required) is a type of string
  admin_network_cidr = null
  # cloud_control_plane_server1 - (required) is a type of string
  cloud_control_plane_server1 = null
  # cloud_control_plane_server2 - (required) is a type of string
  cloud_control_plane_server2 = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # corporate_proxy - (optional) is a type of string
  corporate_proxy = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # dns_server - (required) is a type of list of string
  dns_server = []
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # gateway - (required) is a type of string
  gateway = null
  # infini_band_network_cidr - (required) is a type of string
  infini_band_network_cidr = null
  # netmask - (required) is a type of string
  netmask = null
  # ntp_server - (required) is a type of list of string
  ntp_server = []
  # shape - (required) is a type of string
  shape = null
  # time_zone - (required) is a type of string
  time_zone = null

  contacts = [{
    email                    = null
    is_contact_mos_validated = null
    is_primary               = null
    name                     = null
    phone_number             = null
  }]

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
variable "activation_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_network_cidr" {
  description = "(required)"
  type        = string
}

variable "cloud_control_plane_server1" {
  description = "(required)"
  type        = string
}

variable "cloud_control_plane_server2" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "corporate_proxy" {
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
  description = "(required)"
  type        = string
}

variable "dns_server" {
  description = "(required)"
  type        = list(string)
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "gateway" {
  description = "(required)"
  type        = string
}

variable "infini_band_network_cidr" {
  description = "(required)"
  type        = string
}

variable "netmask" {
  description = "(required)"
  type        = string
}

variable "ntp_server" {
  description = "(required)"
  type        = list(string)
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "time_zone" {
  description = "(required)"
  type        = string
}

variable "contacts" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      email                    = string
      is_contact_mos_validated = bool
      is_primary               = bool
      name                     = string
      phone_number             = string
    }
  ))
  default = []
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
resource "oci_database_exadata_infrastructure" "this" {
  # activation_file - (optional) is a type of string
  activation_file = var.activation_file
  # admin_network_cidr - (required) is a type of string
  admin_network_cidr = var.admin_network_cidr
  # cloud_control_plane_server1 - (required) is a type of string
  cloud_control_plane_server1 = var.cloud_control_plane_server1
  # cloud_control_plane_server2 - (required) is a type of string
  cloud_control_plane_server2 = var.cloud_control_plane_server2
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # corporate_proxy - (optional) is a type of string
  corporate_proxy = var.corporate_proxy
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # dns_server - (required) is a type of list of string
  dns_server = var.dns_server
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # gateway - (required) is a type of string
  gateway = var.gateway
  # infini_band_network_cidr - (required) is a type of string
  infini_band_network_cidr = var.infini_band_network_cidr
  # netmask - (required) is a type of string
  netmask = var.netmask
  # ntp_server - (required) is a type of list of string
  ntp_server = var.ntp_server
  # shape - (required) is a type of string
  shape = var.shape
  # time_zone - (required) is a type of string
  time_zone = var.time_zone

  dynamic "contacts" {
    for_each = var.contacts
    content {
      # email - (required) is a type of string
      email = contacts.value["email"]
      # is_contact_mos_validated - (optional) is a type of bool
      is_contact_mos_validated = contacts.value["is_contact_mos_validated"]
      # is_primary - (required) is a type of bool
      is_primary = contacts.value["is_primary"]
      # name - (required) is a type of string
      name = contacts.value["name"]
      # phone_number - (optional) is a type of string
      phone_number = contacts.value["phone_number"]
    }
  }

  dynamic "maintenance_window" {
    for_each = var.maintenance_window
    content {
      # hours_of_day - (optional) is a type of list of number
      hours_of_day = maintenance_window.value["hours_of_day"]
      # lead_time_in_weeks - (optional) is a type of number
      lead_time_in_weeks = maintenance_window.value["lead_time_in_weeks"]
      # preference - (required) is a type of string
      preference = maintenance_window.value["preference"]
      # weeks_of_month - (optional) is a type of list of number
      weeks_of_month = maintenance_window.value["weeks_of_month"]

      dynamic "days_of_week" {
        for_each = maintenance_window.value.days_of_week
        content {
          # name - (required) is a type of string
          name = days_of_week.value["name"]
        }
      }

      dynamic "months" {
        for_each = maintenance_window.value.months
        content {
          # name - (required) is a type of string
          name = months.value["name"]
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
output "corporate_proxy" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.corporate_proxy
}

output "cpus_enabled" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.cpus_enabled
}

output "csi_number" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.csi_number
}

output "data_storage_size_in_tbs" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.data_storage_size_in_tbs
}

output "db_node_storage_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.db_node_storage_size_in_gbs
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_exadata_infrastructure.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_exadata_infrastructure.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.lifecycle_details
}

output "maintenance_slo_status" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.maintenance_slo_status
}

output "max_cpu_count" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.max_cpu_count
}

output "max_data_storage_in_tbs" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.max_data_storage_in_tbs
}

output "max_db_node_storage_in_gbs" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.max_db_node_storage_in_gbs
}

output "max_memory_in_gbs" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.max_memory_in_gbs
}

output "memory_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_exadata_infrastructure.this.memory_size_in_gbs
}

output "state" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_exadata_infrastructure.this.time_created
}

output "this" {
  value = oci_database_exadata_infrastructure.this
}
```

[top](#index)