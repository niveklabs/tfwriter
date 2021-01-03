# azurerm_app_service_active_slot

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_app_service_active_slot" {
  source = "./modules/azurerm/r/azurerm_app_service_active_slot"

  # app_service_name - (required) is a type of string
  app_service_name = null
  # app_service_slot_name - (required) is a type of string
  app_service_slot_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "app_service_name" {
  description = "(required)"
  type        = string
}

variable "app_service_slot_name" {
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
resource "azurerm_app_service_active_slot" "this" {
  app_service_name      = var.app_service_name
  app_service_slot_name = var.app_service_slot_name
  resource_group_name   = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_app_service_active_slot.this.id
}

output "this" {
  value = azurerm_app_service_active_slot.this
}
```

[top](#index)