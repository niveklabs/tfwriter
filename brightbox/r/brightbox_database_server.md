# brightbox_database_server

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_database_server" {
  source = "./modules/brightbox/r/brightbox_database_server"

  # allow_access - (required) is a type of set of string
  allow_access = []
  # database_engine - (optional) is a type of string
  database_engine = null
  # database_type - (optional) is a type of string
  database_type = null
  # database_version - (optional) is a type of string
  database_version = null
  # description - (optional) is a type of string
  description = null
  # locked - (optional) is a type of bool
  locked = null
  # maintenance_hour - (optional) is a type of number
  maintenance_hour = null
  # maintenance_weekday - (optional) is a type of number
  maintenance_weekday = null
  # name - (optional) is a type of string
  name = null
  # snapshot - (optional) is a type of string
  snapshot = null
  # snapshots_schedule - (optional) is a type of string
  snapshots_schedule = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_access" {
  description = "(required) - An array of resources allowed to access the database. Accepted values include `any`, `IPv4 address`, `server identifier`, `server group identifier`"
  type        = set(string)
}

variable "database_engine" {
  description = "(optional) - The DBMS engine of the Database Server"
  type        = string
  default     = null
}

variable "database_type" {
  description = "(optional) - ID of the database type to use"
  type        = string
  default     = null
}

variable "database_version" {
  description = "(optional) - The version of the given engine in use"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Editable user label"
  type        = string
  default     = null
}

variable "locked" {
  description = "(optional) - Initial password required to login, only available at creation or following a password reset request"
  type        = bool
  default     = null
}

variable "maintenance_hour" {
  description = "(optional) - Number representing 24hr time start of maintenance window hour for x:00-x:59 (0-23)"
  type        = number
  default     = null
}

variable "maintenance_weekday" {
  description = "(optional) - Numerical index of weekday (0 is Sunday, 1 is Monday...) to set when automatic updates may be performed"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - Editable user label"
  type        = string
  default     = null
}

variable "snapshot" {
  description = "(optional) - Identifier for an SQL snapshot to use as the basis of the new instance. Creates and restores the database from the snapshot"
  type        = string
  default     = null
}

variable "snapshots_schedule" {
  description = "(optional) - Crontab pattern for scheduled snapshots. Must be at least hourly"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - ID of the zone the database server is in"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_database_server" "this" {
  allow_access        = var.allow_access
  database_engine     = var.database_engine
  database_type       = var.database_type
  database_version    = var.database_version
  description         = var.description
  locked              = var.locked
  maintenance_hour    = var.maintenance_hour
  maintenance_weekday = var.maintenance_weekday
  name                = var.name
  snapshot            = var.snapshot
  snapshots_schedule  = var.snapshots_schedule
  zone                = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admin_password" {
  description = "returns a string"
  value       = brightbox_database_server.this.admin_password
  sensitive   = true
}

output "admin_username" {
  description = "returns a string"
  value       = brightbox_database_server.this.admin_username
}

output "database_engine" {
  description = "returns a string"
  value       = brightbox_database_server.this.database_engine
}

output "database_type" {
  description = "returns a string"
  value       = brightbox_database_server.this.database_type
}

output "database_version" {
  description = "returns a string"
  value       = brightbox_database_server.this.database_version
}

output "id" {
  description = "returns a string"
  value       = brightbox_database_server.this.id
}

output "maintenance_hour" {
  description = "returns a number"
  value       = brightbox_database_server.this.maintenance_hour
}

output "maintenance_weekday" {
  description = "returns a number"
  value       = brightbox_database_server.this.maintenance_weekday
}

output "snapshots_schedule_next_at" {
  description = "returns a string"
  value       = brightbox_database_server.this.snapshots_schedule_next_at
}

output "status" {
  description = "returns a string"
  value       = brightbox_database_server.this.status
}

output "zone" {
  description = "returns a string"
  value       = brightbox_database_server.this.zone
}

output "this" {
  value = brightbox_database_server.this
}
```

[top](#index)