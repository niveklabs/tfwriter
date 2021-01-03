# azurerm_virtual_machine_extension

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
module "azurerm_virtual_machine_extension" {
  source = "./modules/azurerm/r/azurerm_virtual_machine_extension"

  # auto_upgrade_minor_version - (optional) is a type of bool
  auto_upgrade_minor_version = null
  # name - (required) is a type of string
  name = null
  # protected_settings - (optional) is a type of string
  protected_settings = null
  # publisher - (required) is a type of string
  publisher = null
  # settings - (optional) is a type of string
  settings = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
  # type_handler_version - (required) is a type of string
  type_handler_version = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null

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
variable "auto_upgrade_minor_version" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protected_settings" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publisher" {
  description = "(required)"
  type        = string
}

variable "settings" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "type_handler_version" {
  description = "(required)"
  type        = string
}

variable "virtual_machine_id" {
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
resource "azurerm_virtual_machine_extension" "this" {
  auto_upgrade_minor_version = var.auto_upgrade_minor_version
  name                       = var.name
  protected_settings         = var.protected_settings
  publisher                  = var.publisher
  settings                   = var.settings
  tags                       = var.tags
  type                       = var.type
  type_handler_version       = var.type_handler_version
  virtual_machine_id         = var.virtual_machine_id

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
  value       = azurerm_virtual_machine_extension.this.id
}

output "this" {
  value = azurerm_virtual_machine_extension.this
}
```

[top](#index)