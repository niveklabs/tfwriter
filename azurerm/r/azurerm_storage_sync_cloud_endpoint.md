# azurerm_storage_sync_cloud_endpoint

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
module "azurerm_storage_sync_cloud_endpoint" {
  source = "./modules/azurerm/r/azurerm_storage_sync_cloud_endpoint"

  # file_share_name - (required) is a type of string
  file_share_name = null
  # name - (required) is a type of string
  name = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null
  # storage_account_tenant_id - (optional) is a type of string
  storage_account_tenant_id = null
  # storage_sync_group_id - (required) is a type of string
  storage_sync_group_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "file_share_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "storage_account_id" {
  description = "(required)"
  type        = string
}

variable "storage_account_tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_sync_group_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_storage_sync_cloud_endpoint" "this" {
  # file_share_name - (required) is a type of string
  file_share_name = var.file_share_name
  # name - (required) is a type of string
  name = var.name
  # storage_account_id - (required) is a type of string
  storage_account_id = var.storage_account_id
  # storage_account_tenant_id - (optional) is a type of string
  storage_account_tenant_id = var.storage_account_tenant_id
  # storage_sync_group_id - (required) is a type of string
  storage_sync_group_id = var.storage_sync_group_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_storage_sync_cloud_endpoint.this.id
}

output "storage_account_tenant_id" {
  description = "returns a string"
  value       = azurerm_storage_sync_cloud_endpoint.this.storage_account_tenant_id
}

output "this" {
  value = azurerm_storage_sync_cloud_endpoint.this
}
```

[top](#index)