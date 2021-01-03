# oraclepaas_mysql_service_instance

[back](../oraclepaas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oraclepaas = ">= 1.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oraclepaas_mysql_service_instance" {
  source = "./modules/oraclepaas/r/oraclepaas_mysql_service_instance"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # backup_destination - (optional) is a type of string
  backup_destination = null
  # description - (optional) is a type of string
  description = null
  # ip_network - (optional) is a type of string
  ip_network = null
  # metering_frequency - (optional) is a type of string
  metering_frequency = null
  # name - (required) is a type of string
  name = null
  # notification_email - (optional) is a type of string
  notification_email = null
  # region - (optional) is a type of string
  region = null
  # shape - (required) is a type of string
  shape = null
  # ssh_public_key - (required) is a type of string
  ssh_public_key = null
  # subnet - (optional) is a type of string
  subnet = null
  # vm_user - (optional) is a type of string
  vm_user = null

  backups = [{
    cloud_storage_container = null
    cloud_storage_password  = null
    cloud_storage_username  = null
    create_if_missing       = null
  }]

  mysql_configuration = [{
    connect_string = null
    db_name        = null
    db_storage     = null
    enterprise_monitor_configuration = [{
      em_agent_password = null
      em_agent_username = null
      em_password       = null
      em_port           = null
      em_username       = null
    }]
    ip_address          = null
    mysql_charset       = null
    mysql_collation     = null
    mysql_password      = null
    mysql_port          = null
    mysql_username      = null
    public_ip_address   = null
    snapshot_name       = null
    source_service_name = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metering_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "ssh_public_key" {
  description = "(required)"
  type        = string
}

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backups" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_storage_container = string
      cloud_storage_password  = string
      cloud_storage_username  = string
      create_if_missing       = bool
    }
  ))
  default = []
}

variable "mysql_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      connect_string = string
      db_name        = string
      db_storage     = number
      enterprise_monitor_configuration = list(object(
        {
          em_agent_password = string
          em_agent_username = string
          em_password       = string
          em_port           = number
          em_username       = string
        }
      ))
      ip_address          = string
      mysql_charset       = string
      mysql_collation     = string
      mysql_password      = string
      mysql_port          = number
      mysql_username      = string
      public_ip_address   = string
      snapshot_name       = string
      source_service_name = string
    }
  ))
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
resource "oraclepaas_mysql_service_instance" "this" {
  availability_domain = var.availability_domain
  backup_destination  = var.backup_destination
  description         = var.description
  ip_network          = var.ip_network
  metering_frequency  = var.metering_frequency
  name                = var.name
  notification_email  = var.notification_email
  region              = var.region
  shape               = var.shape
  ssh_public_key      = var.ssh_public_key
  subnet              = var.subnet
  vm_user             = var.vm_user

  dynamic "backups" {
    for_each = var.backups
    content {
      cloud_storage_container = backups.value["cloud_storage_container"]
      cloud_storage_password  = backups.value["cloud_storage_password"]
      cloud_storage_username  = backups.value["cloud_storage_username"]
      create_if_missing       = backups.value["create_if_missing"]
    }
  }

  dynamic "mysql_configuration" {
    for_each = var.mysql_configuration
    content {
      db_name             = mysql_configuration.value["db_name"]
      db_storage          = mysql_configuration.value["db_storage"]
      mysql_charset       = mysql_configuration.value["mysql_charset"]
      mysql_collation     = mysql_configuration.value["mysql_collation"]
      mysql_password      = mysql_configuration.value["mysql_password"]
      mysql_port          = mysql_configuration.value["mysql_port"]
      mysql_username      = mysql_configuration.value["mysql_username"]
      snapshot_name       = mysql_configuration.value["snapshot_name"]
      source_service_name = mysql_configuration.value["source_service_name"]

      dynamic "enterprise_monitor_configuration" {
        for_each = mysql_configuration.value.enterprise_monitor_configuration
        content {
          em_agent_password = enterprise_monitor_configuration.value["em_agent_password"]
          em_agent_username = enterprise_monitor_configuration.value["em_agent_username"]
          em_password       = enterprise_monitor_configuration.value["em_password"]
          em_port           = enterprise_monitor_configuration.value["em_port"]
          em_username       = enterprise_monitor_configuration.value["em_username"]
        }
      }

    }
  }

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
output "base_release_version" {
  description = "returns a string"
  value       = oraclepaas_mysql_service_instance.this.base_release_version
}

output "em_url" {
  description = "returns a string"
  value       = oraclepaas_mysql_service_instance.this.em_url
}

output "id" {
  description = "returns a string"
  value       = oraclepaas_mysql_service_instance.this.id
}

output "region" {
  description = "returns a string"
  value       = oraclepaas_mysql_service_instance.this.region
}

output "release_version" {
  description = "returns a string"
  value       = oraclepaas_mysql_service_instance.this.release_version
}

output "service_version" {
  description = "returns a string"
  value       = oraclepaas_mysql_service_instance.this.service_version
}

output "this" {
  value = oraclepaas_mysql_service_instance.this
}
```

[top](#index)