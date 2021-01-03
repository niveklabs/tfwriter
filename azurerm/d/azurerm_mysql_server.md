# azurerm_mysql_server

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mysql_server" {
  source = "./modules/azurerm/d/azurerm_mysql_server"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_mysql_server" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "administrator_login" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.administrator_login
}

output "auto_grow_enabled" {
  description = "returns a bool"
  value       = data.azurerm_mysql_server.this.auto_grow_enabled
}

output "backup_retention_days" {
  description = "returns a number"
  value       = data.azurerm_mysql_server.this.backup_retention_days
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.fqdn
}

output "geo_redundant_backup_enabled" {
  description = "returns a bool"
  value       = data.azurerm_mysql_server.this.geo_redundant_backup_enabled
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_mysql_server.this.identity
}

output "infrastructure_encryption_enabled" {
  description = "returns a bool"
  value       = data.azurerm_mysql_server.this.infrastructure_encryption_enabled
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.location
}

output "public_network_access_enabled" {
  description = "returns a bool"
  value       = data.azurerm_mysql_server.this.public_network_access_enabled
}

output "restore_point_in_time" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.restore_point_in_time
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.sku_name
}

output "ssl_enforcement_enabled" {
  description = "returns a bool"
  value       = data.azurerm_mysql_server.this.ssl_enforcement_enabled
}

output "ssl_minimal_tls_version_enforced" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.ssl_minimal_tls_version_enforced
}

output "storage_mb" {
  description = "returns a number"
  value       = data.azurerm_mysql_server.this.storage_mb
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_mysql_server.this.tags
}

output "threat_detection_policy" {
  description = "returns a list of object"
  value       = data.azurerm_mysql_server.this.threat_detection_policy
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_mysql_server.this.version
}

output "this" {
  value = azurerm_mysql_server.this
}
```

[top](#index)