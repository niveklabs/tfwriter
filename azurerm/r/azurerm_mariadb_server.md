# azurerm_mariadb_server

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mariadb_server" {
  source = "./modules/azurerm/r/azurerm_mariadb_server"

  # administrator_login - (optional) is a type of string
  administrator_login = null
  # administrator_login_password - (optional) is a type of string
  administrator_login_password = null
  # auto_grow_enabled - (optional) is a type of bool
  auto_grow_enabled = null
  # backup_retention_days - (optional) is a type of number
  backup_retention_days = null
  # create_mode - (optional) is a type of string
  create_mode = null
  # creation_source_server_id - (optional) is a type of string
  creation_source_server_id = null
  # geo_redundant_backup_enabled - (optional) is a type of bool
  geo_redundant_backup_enabled = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # restore_point_in_time - (optional) is a type of string
  restore_point_in_time = null
  # sku_name - (required) is a type of string
  sku_name = null
  # ssl_enforcement - (optional) is a type of string
  ssl_enforcement = null
  # ssl_enforcement_enabled - (optional) is a type of bool
  ssl_enforcement_enabled = null
  # storage_mb - (optional) is a type of number
  storage_mb = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (required) is a type of string
  version = null

  storage_profile = [{
    auto_grow             = null
    backup_retention_days = null
    geo_redundant_backup  = null
    storage_mb            = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "administrator_login" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "administrator_login_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_grow_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "backup_retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "create_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "creation_source_server_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geo_redundant_backup_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_network_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "restore_point_in_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "ssl_enforcement" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_enforcement_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_mb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "storage_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_grow             = string
      backup_retention_days = number
      geo_redundant_backup  = string
      storage_mb            = number
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
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_mariadb_server" "this" {
  # administrator_login - (optional) is a type of string
  administrator_login = var.administrator_login
  # administrator_login_password - (optional) is a type of string
  administrator_login_password = var.administrator_login_password
  # auto_grow_enabled - (optional) is a type of bool
  auto_grow_enabled = var.auto_grow_enabled
  # backup_retention_days - (optional) is a type of number
  backup_retention_days = var.backup_retention_days
  # create_mode - (optional) is a type of string
  create_mode = var.create_mode
  # creation_source_server_id - (optional) is a type of string
  creation_source_server_id = var.creation_source_server_id
  # geo_redundant_backup_enabled - (optional) is a type of bool
  geo_redundant_backup_enabled = var.geo_redundant_backup_enabled
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = var.public_network_access_enabled
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # restore_point_in_time - (optional) is a type of string
  restore_point_in_time = var.restore_point_in_time
  # sku_name - (required) is a type of string
  sku_name = var.sku_name
  # ssl_enforcement - (optional) is a type of string
  ssl_enforcement = var.ssl_enforcement
  # ssl_enforcement_enabled - (optional) is a type of bool
  ssl_enforcement_enabled = var.ssl_enforcement_enabled
  # storage_mb - (optional) is a type of number
  storage_mb = var.storage_mb
  # tags - (optional) is a type of map of string
  tags = var.tags
  # version - (required) is a type of string
  version = var.version

  dynamic "storage_profile" {
    for_each = var.storage_profile
    content {
      # auto_grow - (optional) is a type of string
      auto_grow = storage_profile.value["auto_grow"]
      # backup_retention_days - (optional) is a type of number
      backup_retention_days = storage_profile.value["backup_retention_days"]
      # geo_redundant_backup - (optional) is a type of string
      geo_redundant_backup = storage_profile.value["geo_redundant_backup"]
      # storage_mb - (optional) is a type of number
      storage_mb = storage_profile.value["storage_mb"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "administrator_login" {
  description = "returns a string"
  value       = azurerm_mariadb_server.this.administrator_login
}

output "auto_grow_enabled" {
  description = "returns a bool"
  value       = azurerm_mariadb_server.this.auto_grow_enabled
}

output "backup_retention_days" {
  description = "returns a number"
  value       = azurerm_mariadb_server.this.backup_retention_days
}

output "fqdn" {
  description = "returns a string"
  value       = azurerm_mariadb_server.this.fqdn
}

output "geo_redundant_backup_enabled" {
  description = "returns a bool"
  value       = azurerm_mariadb_server.this.geo_redundant_backup_enabled
}

output "id" {
  description = "returns a string"
  value       = azurerm_mariadb_server.this.id
}

output "ssl_enforcement" {
  description = "returns a string"
  value       = azurerm_mariadb_server.this.ssl_enforcement
}

output "storage_mb" {
  description = "returns a number"
  value       = azurerm_mariadb_server.this.storage_mb
}

output "this" {
  value = azurerm_mariadb_server.this
}
```

[top](#index)