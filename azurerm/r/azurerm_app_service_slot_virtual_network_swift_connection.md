# azurerm_app_service_slot_virtual_network_swift_connection

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
module "azurerm_app_service_slot_virtual_network_swift_connection" {
  source = "./modules/azurerm/r/azurerm_app_service_slot_virtual_network_swift_connection"

  # app_service_id - (required) is a type of string
  app_service_id = null
  # slot_name - (required) is a type of string
  slot_name = null
  # subnet_id - (required) is a type of string
  subnet_id = null

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
variable "app_service_id" {
  description = "(required)"
  type        = string
}

variable "slot_name" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
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
resource "azurerm_app_service_slot_virtual_network_swift_connection" "this" {
  # app_service_id - (required) is a type of string
  app_service_id = var.app_service_id
  # slot_name - (required) is a type of string
  slot_name = var.slot_name
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id

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
output "id" {
  description = "returns a string"
  value       = azurerm_app_service_slot_virtual_network_swift_connection.this.id
}

output "this" {
  value = azurerm_app_service_slot_virtual_network_swift_connection.this
}
```

[top](#index)