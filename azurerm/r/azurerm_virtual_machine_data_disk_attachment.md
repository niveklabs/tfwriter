# azurerm_virtual_machine_data_disk_attachment

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
module "azurerm_virtual_machine_data_disk_attachment" {
  source = "./modules/azurerm/r/azurerm_virtual_machine_data_disk_attachment"

  # caching - (required) is a type of string
  caching = null
  # create_option - (optional) is a type of string
  create_option = null
  # lun - (required) is a type of number
  lun = null
  # managed_disk_id - (required) is a type of string
  managed_disk_id = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null
  # write_accelerator_enabled - (optional) is a type of bool
  write_accelerator_enabled = null

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
variable "caching" {
  description = "(required)"
  type        = string
}

variable "create_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lun" {
  description = "(required)"
  type        = number
}

variable "managed_disk_id" {
  description = "(required)"
  type        = string
}

variable "virtual_machine_id" {
  description = "(required)"
  type        = string
}

variable "write_accelerator_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
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
resource "azurerm_virtual_machine_data_disk_attachment" "this" {
  caching                   = var.caching
  create_option             = var.create_option
  lun                       = var.lun
  managed_disk_id           = var.managed_disk_id
  virtual_machine_id        = var.virtual_machine_id
  write_accelerator_enabled = var.write_accelerator_enabled

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
  value       = azurerm_virtual_machine_data_disk_attachment.this.id
}

output "this" {
  value = azurerm_virtual_machine_data_disk_attachment.this
}
```

[top](#index)