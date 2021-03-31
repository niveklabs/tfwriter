# azurerm_storage_container

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
module "azurerm_storage_container" {
  source = "./modules/azurerm/d/azurerm_storage_container"

  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_storage_container" "this" {
  metadata             = var.metadata
  name                 = var.name
  storage_account_name = var.storage_account_name

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
output "container_access_type" {
  description = "returns a string"
  value       = data.azurerm_storage_container.this.container_access_type
}

output "has_immutability_policy" {
  description = "returns a bool"
  value       = data.azurerm_storage_container.this.has_immutability_policy
}

output "has_legal_hold" {
  description = "returns a bool"
  value       = data.azurerm_storage_container.this.has_legal_hold
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_storage_container.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.azurerm_storage_container.this.metadata
}

output "resource_manager_id" {
  description = "returns a string"
  value       = data.azurerm_storage_container.this.resource_manager_id
}

output "this" {
  value = azurerm_storage_container.this
}
```

[top](#index)