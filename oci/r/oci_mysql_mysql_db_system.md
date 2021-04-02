# oci_mysql_mysql_db_system

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_mysql_mysql_db_system" {
  source = [{
    backup_id   = null
    source_type = null
  }]

  # admin_password - (required) is a type of string
  admin_password = null
  # admin_username - (required) is a type of string
  admin_username = null
  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # configuration_id - (optional) is a type of string
  configuration_id = null
  # data_storage_size_in_gb - (optional) is a type of number
  data_storage_size_in_gb = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # fault_domain - (optional) is a type of string
  fault_domain = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hostname_label - (optional) is a type of string
  hostname_label = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # mysql_version - (optional) is a type of string
  mysql_version = null
  # port - (optional) is a type of number
  port = null
  # port_x - (optional) is a type of number
  port_x = null
  # shape_name - (required) is a type of string
  shape_name = null
  # shutdown_type - (optional) is a type of string
  shutdown_type = null
  # state - (optional) is a type of string
  state = null
  # subnet_id - (required) is a type of string
  subnet_id = null

  backup_policy = [{
    defined_tags      = {}
    freeform_tags     = {}
    is_enabled        = null
    retention_in_days = null
    window_start_time = null
  }]

  maintenance = [{
    window_start_time = null
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
variable "admin_password" {
  description = "(required)"
  type        = string
}

variable "admin_username" {
  description = "(required)"
  type        = string
}

variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "configuration_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_storage_size_in_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fault_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hostname_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mysql_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_x" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shape_name" {
  description = "(required)"
  type        = string
}

variable "shutdown_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "backup_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      defined_tags      = map(string)
      freeform_tags     = map(string)
      is_enabled        = bool
      retention_in_days = number
      window_start_time = string
    }
  ))
  default = []
}

variable "maintenance" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      window_start_time = string
    }
  ))
  default = []
}

variable "source" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      backup_id   = string
      source_type = string
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
resource "oci_mysql_mysql_db_system" "this" {
  admin_password          = var.admin_password
  admin_username          = var.admin_username
  availability_domain     = var.availability_domain
  compartment_id          = var.compartment_id
  configuration_id        = var.configuration_id
  data_storage_size_in_gb = var.data_storage_size_in_gb
  defined_tags            = var.defined_tags
  description             = var.description
  display_name            = var.display_name
  fault_domain            = var.fault_domain
  freeform_tags           = var.freeform_tags
  hostname_label          = var.hostname_label
  ip_address              = var.ip_address
  mysql_version           = var.mysql_version
  port                    = var.port
  port_x                  = var.port_x
  shape_name              = var.shape_name
  shutdown_type           = var.shutdown_type
  state                   = var.state
  subnet_id               = var.subnet_id

  dynamic "backup_policy" {
    for_each = var.backup_policy
    content {
      defined_tags      = backup_policy.value["defined_tags"]
      freeform_tags     = backup_policy.value["freeform_tags"]
      is_enabled        = backup_policy.value["is_enabled"]
      retention_in_days = backup_policy.value["retention_in_days"]
      window_start_time = backup_policy.value["window_start_time"]
    }
  }

  dynamic "maintenance" {
    for_each = var.maintenance
    content {
      window_start_time = maintenance.value["window_start_time"]
    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      backup_id   = source.value["backup_id"]
      source_type = source.value["source_type"]
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
output "analytics_cluster" {
  description = "returns a list of object"
  value       = oci_mysql_mysql_db_system.this.analytics_cluster
}

output "channels" {
  description = "returns a list of object"
  value       = oci_mysql_mysql_db_system.this.channels
}

output "configuration_id" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.configuration_id
}

output "data_storage_size_in_gb" {
  description = "returns a number"
  value       = oci_mysql_mysql_db_system.this.data_storage_size_in_gb
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_mysql_mysql_db_system.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.display_name
}

output "endpoints" {
  description = "returns a list of object"
  value       = oci_mysql_mysql_db_system.this.endpoints
}

output "fault_domain" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.fault_domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_mysql_mysql_db_system.this.freeform_tags
}

output "heat_wave_cluster" {
  description = "returns a list of object"
  value       = oci_mysql_mysql_db_system.this.heat_wave_cluster
}

output "hostname_label" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.hostname_label
}

output "id" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.ip_address
}

output "is_analytics_cluster_attached" {
  description = "returns a bool"
  value       = oci_mysql_mysql_db_system.this.is_analytics_cluster_attached
}

output "is_heat_wave_cluster_attached" {
  description = "returns a bool"
  value       = oci_mysql_mysql_db_system.this.is_heat_wave_cluster_attached
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.lifecycle_details
}

output "mysql_version" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.mysql_version
}

output "port" {
  description = "returns a number"
  value       = oci_mysql_mysql_db_system.this.port
}

output "port_x" {
  description = "returns a number"
  value       = oci_mysql_mysql_db_system.this.port_x
}

output "state" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_mysql_mysql_db_system.this.time_updated
}

output "this" {
  value = oci_mysql_mysql_db_system.this
}
```

[top](#index)