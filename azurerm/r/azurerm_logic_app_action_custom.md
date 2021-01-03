# azurerm_logic_app_action_custom

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
module "azurerm_logic_app_action_custom" {
  source = "./modules/azurerm/r/azurerm_logic_app_action_custom"

  # body - (required) is a type of string
  body = null
  # logic_app_id - (required) is a type of string
  logic_app_id = null
  # name - (required) is a type of string
  name = null

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
variable "body" {
  description = "(required)"
  type        = string
}

variable "logic_app_id" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "azurerm_logic_app_action_custom" "this" {
  body         = var.body
  logic_app_id = var.logic_app_id
  name         = var.name

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
  value       = azurerm_logic_app_action_custom.this.id
}

output "this" {
  value = azurerm_logic_app_action_custom.this
}
```

[top](#index)