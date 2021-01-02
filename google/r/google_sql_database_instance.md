# google_sql_database_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_sql_database_instance" {
  source = "./modules/google/r/google_sql_database_instance"

  # database_version - (optional) is a type of string
  database_version = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # master_instance_name - (optional) is a type of string
  master_instance_name = null
  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # root_password - (optional) is a type of string
  root_password = null

  replica_configuration = [{
    ca_certificate            = null
    client_certificate        = null
    client_key                = null
    connect_retry_interval    = null
    dump_file_path            = null
    failover_target           = null
    master_heartbeat_period   = null
    password                  = null
    ssl_cipher                = null
    username                  = null
    verify_server_certificate = null
  }]

  settings = [{
    activation_policy           = null
    authorized_gae_applications = []
    availability_type           = null
    backup_configuration = [{
      binary_log_enabled             = null
      enabled                        = null
      location                       = null
      point_in_time_recovery_enabled = null
      start_time                     = null
    }]
    crash_safe_replication = null
    database_flags = [{
      name  = null
      value = null
    }]
    disk_autoresize = null
    disk_size       = null
    disk_type       = null
    ip_configuration = [{
      authorized_networks = [{
        expiration_time = null
        name            = null
        value           = null
      }]
      ipv4_enabled    = null
      private_network = null
      require_ssl     = null
    }]
    location_preference = [{
      follow_gae_application = null
      zone                   = null
    }]
    maintenance_window = [{
      day          = null
      hour         = null
      update_track = null
    }]
    pricing_plan     = null
    replication_type = null
    tier             = null
    user_labels      = {}
    version          = null
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
variable "database_version" {
  description = "(optional) - The MySQL, PostgreSQL or SQL Server (beta) version to use. Supported values include MYSQL_5_6, MYSQL_5_7, POSTGRES_9_6,POSTGRES_11, SQLSERVER_2017_STANDARD, SQLSERVER_2017_ENTERPRISE, SQLSERVER_2017_EXPRESS, SQLSERVER_2017_WEB. Database Version Policies includes an up-to-date reference of supported versions."
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional) - Used to block Terraform from deleting a SQL Instance."
  type        = bool
  default     = null
}

variable "master_instance_name" {
  description = "(optional) - The name of the instance that will act as the master in the replication setup. Note, this requires the master to have binary_log_enabled set, as well as existing backups."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the instance. If the name is left blank, Terraform will randomly generate one when the instance is first created. This is done because after a name is used, it cannot be reused for up to one week."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region the instance will sit in. Note, Cloud SQL is not available in all regions - choose from one of the options listed here. A valid region must be provided to use this resource. If a region is not provided in the resource definition, the provider region will be used instead, but this will be an apply-time error for instances if the provider region is not supported with Cloud SQL. If you choose not to provide the region argument for this resource, make sure you understand this."
  type        = string
  default     = null
}

variable "root_password" {
  description = "(optional) - Initial root password. Required for MS SQL Server, ignored by MySQL and PostgreSQL."
  type        = string
  default     = null
}

variable "replica_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ca_certificate            = string
      client_certificate        = string
      client_key                = string
      connect_retry_interval    = number
      dump_file_path            = string
      failover_target           = bool
      master_heartbeat_period   = number
      password                  = string
      ssl_cipher                = string
      username                  = string
      verify_server_certificate = bool
    }
  ))
  default = []
}

variable "settings" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      activation_policy           = string
      authorized_gae_applications = list(string)
      availability_type           = string
      backup_configuration = list(object(
        {
          binary_log_enabled             = bool
          enabled                        = bool
          location                       = string
          point_in_time_recovery_enabled = bool
          start_time                     = string
        }
      ))
      crash_safe_replication = bool
      database_flags = list(object(
        {
          name  = string
          value = string
        }
      ))
      disk_autoresize = bool
      disk_size       = number
      disk_type       = string
      ip_configuration = list(object(
        {
          authorized_networks = set(object(
            {
              expiration_time = string
              name            = string
              value           = string
            }
          ))
          ipv4_enabled    = bool
          private_network = string
          require_ssl     = bool
        }
      ))
      location_preference = list(object(
        {
          follow_gae_application = string
          zone                   = string
        }
      ))
      maintenance_window = list(object(
        {
          day          = number
          hour         = number
          update_track = string
        }
      ))
      pricing_plan     = string
      replication_type = string
      tier             = string
      user_labels      = map(string)
      version          = number
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
resource "google_sql_database_instance" "this" {
  database_version     = var.database_version
  deletion_protection  = var.deletion_protection
  master_instance_name = var.master_instance_name
  name                 = var.name
  project              = var.project
  region               = var.region
  root_password        = var.root_password

  dynamic "replica_configuration" {
    for_each = var.replica_configuration
    content {
      ca_certificate            = replica_configuration.value["ca_certificate"]
      client_certificate        = replica_configuration.value["client_certificate"]
      client_key                = replica_configuration.value["client_key"]
      connect_retry_interval    = replica_configuration.value["connect_retry_interval"]
      dump_file_path            = replica_configuration.value["dump_file_path"]
      failover_target           = replica_configuration.value["failover_target"]
      master_heartbeat_period   = replica_configuration.value["master_heartbeat_period"]
      password                  = replica_configuration.value["password"]
      ssl_cipher                = replica_configuration.value["ssl_cipher"]
      username                  = replica_configuration.value["username"]
      verify_server_certificate = replica_configuration.value["verify_server_certificate"]
    }
  }

  dynamic "settings" {
    for_each = var.settings
    content {
      activation_policy           = settings.value["activation_policy"]
      authorized_gae_applications = settings.value["authorized_gae_applications"]
      availability_type           = settings.value["availability_type"]
      crash_safe_replication      = settings.value["crash_safe_replication"]
      disk_autoresize             = settings.value["disk_autoresize"]
      disk_size                   = settings.value["disk_size"]
      disk_type                   = settings.value["disk_type"]
      pricing_plan                = settings.value["pricing_plan"]
      replication_type            = settings.value["replication_type"]
      tier                        = settings.value["tier"]
      user_labels                 = settings.value["user_labels"]

      dynamic "backup_configuration" {
        for_each = settings.value.backup_configuration
        content {
          binary_log_enabled             = backup_configuration.value["binary_log_enabled"]
          enabled                        = backup_configuration.value["enabled"]
          location                       = backup_configuration.value["location"]
          point_in_time_recovery_enabled = backup_configuration.value["point_in_time_recovery_enabled"]
          start_time                     = backup_configuration.value["start_time"]
        }
      }

      dynamic "database_flags" {
        for_each = settings.value.database_flags
        content {
          name  = database_flags.value["name"]
          value = database_flags.value["value"]
        }
      }

      dynamic "ip_configuration" {
        for_each = settings.value.ip_configuration
        content {
          ipv4_enabled    = ip_configuration.value["ipv4_enabled"]
          private_network = ip_configuration.value["private_network"]
          require_ssl     = ip_configuration.value["require_ssl"]

          dynamic "authorized_networks" {
            for_each = ip_configuration.value.authorized_networks
            content {
              expiration_time = authorized_networks.value["expiration_time"]
              name            = authorized_networks.value["name"]
              value           = authorized_networks.value["value"]
            }
          }

        }
      }

      dynamic "location_preference" {
        for_each = settings.value.location_preference
        content {
          follow_gae_application = location_preference.value["follow_gae_application"]
          zone                   = location_preference.value["zone"]
        }
      }

      dynamic "maintenance_window" {
        for_each = settings.value.maintenance_window
        content {
          day          = maintenance_window.value["day"]
          hour         = maintenance_window.value["hour"]
          update_track = maintenance_window.value["update_track"]
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
output "connection_name" {
  description = "returns a string"
  value       = google_sql_database_instance.this.connection_name
}

output "first_ip_address" {
  description = "returns a string"
  value       = google_sql_database_instance.this.first_ip_address
}

output "id" {
  description = "returns a string"
  value       = google_sql_database_instance.this.id
}

output "ip_address" {
  description = "returns a list of object"
  value       = google_sql_database_instance.this.ip_address
}

output "master_instance_name" {
  description = "returns a string"
  value       = google_sql_database_instance.this.master_instance_name
}

output "name" {
  description = "returns a string"
  value       = google_sql_database_instance.this.name
}

output "private_ip_address" {
  description = "returns a string"
  value       = google_sql_database_instance.this.private_ip_address
}

output "project" {
  description = "returns a string"
  value       = google_sql_database_instance.this.project
}

output "public_ip_address" {
  description = "returns a string"
  value       = google_sql_database_instance.this.public_ip_address
}

output "region" {
  description = "returns a string"
  value       = google_sql_database_instance.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_sql_database_instance.this.self_link
}

output "server_ca_cert" {
  description = "returns a list of object"
  value       = google_sql_database_instance.this.server_ca_cert
}

output "service_account_email_address" {
  description = "returns a string"
  value       = google_sql_database_instance.this.service_account_email_address
}

output "this" {
  value = google_sql_database_instance.this
}
```

[top](#index)