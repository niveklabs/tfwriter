# azurerm_virtual_machine_scale_set_extension

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_virtual_machine_scale_set_extension" {
  source = "./modules/azurerm/r/azurerm_virtual_machine_scale_set_extension"

  # auto_upgrade_minor_version - (optional) is a type of bool
  auto_upgrade_minor_version = null
  # force_update_tag - (optional) is a type of string
  force_update_tag = null
  # name - (required) is a type of string
  name = null
  # protected_settings - (optional) is a type of string
  protected_settings = null
  # provision_after_extensions - (optional) is a type of list of string
  provision_after_extensions = []
  # publisher - (required) is a type of string
  publisher = null
  # settings - (optional) is a type of string
  settings = null
  # type - (required) is a type of string
  type = null
  # type_handler_version - (required) is a type of string
  type_handler_version = null
  # virtual_machine_scale_set_id - (required) is a type of string
  virtual_machine_scale_set_id = null

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

variable "force_update_tag" {
  description = "(optional)"
  type        = string
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

variable "provision_after_extensions" {
  description = "(optional)"
  type        = list(string)
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

variable "type" {
  description = "(required)"
  type        = string
}

variable "type_handler_version" {
  description = "(required)"
  type        = string
}

variable "virtual_machine_scale_set_id" {
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
resource "azurerm_virtual_machine_scale_set_extension" "this" {
  auto_upgrade_minor_version   = var.auto_upgrade_minor_version
  force_update_tag             = var.force_update_tag
  name                         = var.name
  protected_settings           = var.protected_settings
  provision_after_extensions   = var.provision_after_extensions
  publisher                    = var.publisher
  settings                     = var.settings
  type                         = var.type
  type_handler_version         = var.type_handler_version
  virtual_machine_scale_set_id = var.virtual_machine_scale_set_id

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
  value       = azurerm_virtual_machine_scale_set_extension.this.id
}

output "this" {
  value = azurerm_virtual_machine_scale_set_extension.this
}
```

[top](#index)