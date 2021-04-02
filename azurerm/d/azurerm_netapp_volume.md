# azurerm_netapp_volume

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_netapp_volume" {
  source = "./modules/azurerm/d/azurerm_netapp_volume"

  # account_name - (required) is a type of string
  account_name = null
  # name - (required) is a type of string
  name = null
  # pool_name - (required) is a type of string
  pool_name = null
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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pool_name" {
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
data "azurerm_netapp_volume" "this" {
  account_name        = var.account_name
  name                = var.name
  pool_name           = var.pool_name
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
output "data_protection_replication" {
  description = "returns a list of object"
  value       = data.azurerm_netapp_volume.this.data_protection_replication
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_netapp_volume.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_netapp_volume.this.location
}

output "mount_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_netapp_volume.this.mount_ip_addresses
}

output "protocols" {
  description = "returns a list of string"
  value       = data.azurerm_netapp_volume.this.protocols
}

output "service_level" {
  description = "returns a string"
  value       = data.azurerm_netapp_volume.this.service_level
}

output "storage_quota_in_gb" {
  description = "returns a number"
  value       = data.azurerm_netapp_volume.this.storage_quota_in_gb
}

output "subnet_id" {
  description = "returns a string"
  value       = data.azurerm_netapp_volume.this.subnet_id
}

output "volume_path" {
  description = "returns a string"
  value       = data.azurerm_netapp_volume.this.volume_path
}

output "this" {
  value = azurerm_netapp_volume.this
}
```

[top](#index)