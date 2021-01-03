# azurerm_managed_disk

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
module "azurerm_managed_disk" {
  source = "./modules/azurerm/d/azurerm_managed_disk"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
data "azurerm_managed_disk" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags
  zones               = var.zones

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
output "create_option" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.create_option
}

output "disk_encryption_set_id" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.disk_encryption_set_id
}

output "disk_iops_read_write" {
  description = "returns a number"
  value       = data.azurerm_managed_disk.this.disk_iops_read_write
}

output "disk_mbps_read_write" {
  description = "returns a number"
  value       = data.azurerm_managed_disk.this.disk_mbps_read_write
}

output "disk_size_gb" {
  description = "returns a number"
  value       = data.azurerm_managed_disk.this.disk_size_gb
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.id
}

output "image_reference_id" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.image_reference_id
}

output "os_type" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.os_type
}

output "source_resource_id" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.source_resource_id
}

output "source_uri" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.source_uri
}

output "storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.storage_account_id
}

output "storage_account_type" {
  description = "returns a string"
  value       = data.azurerm_managed_disk.this.storage_account_type
}

output "zones" {
  description = "returns a list of string"
  value       = data.azurerm_managed_disk.this.zones
}

output "this" {
  value = azurerm_managed_disk.this
}
```

[top](#index)