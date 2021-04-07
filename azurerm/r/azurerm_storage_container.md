# azurerm_storage_container

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
module "azurerm_storage_container" {
  source = "./modules/azurerm/r/azurerm_storage_container"

  # container_access_type - (optional) is a type of string
  container_access_type = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null

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
variable "container_access_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "storage_account_name" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_storage_container" "this" {
  # container_access_type - (optional) is a type of string
  container_access_type = var.container_access_type
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # storage_account_name - (required) is a type of string
  storage_account_name = var.storage_account_name

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
output "has_immutability_policy" {
  description = "returns a bool"
  value       = azurerm_storage_container.this.has_immutability_policy
}

output "has_legal_hold" {
  description = "returns a bool"
  value       = azurerm_storage_container.this.has_legal_hold
}

output "id" {
  description = "returns a string"
  value       = azurerm_storage_container.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = azurerm_storage_container.this.metadata
}

output "resource_manager_id" {
  description = "returns a string"
  value       = azurerm_storage_container.this.resource_manager_id
}

output "this" {
  value = azurerm_storage_container.this
}
```

[top](#index)