# azurerm_container_registry

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_container_registry" {
  source = "./modules/azurerm/d/azurerm_container_registry"

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
data "azurerm_container_registry" "this" {
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
output "admin_enabled" {
  description = "returns a bool"
  value       = data.azurerm_container_registry.this.admin_enabled
}

output "admin_password" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.admin_password
}

output "admin_username" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.admin_username
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.location
}

output "login_server" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.login_server
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.sku
}

output "storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_container_registry.this.storage_account_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_container_registry.this.tags
}

output "this" {
  value = azurerm_container_registry.this
}
```

[top](#index)