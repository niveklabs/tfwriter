# azurerm_maintenance_assignment_virtual_machine

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
module "azurerm_maintenance_assignment_virtual_machine" {
  source = "./modules/azurerm/r/azurerm_maintenance_assignment_virtual_machine"

  # location - (required) is a type of string
  location = null
  # maintenance_configuration_id - (required) is a type of string
  maintenance_configuration_id = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null

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
variable "location" {
  description = "(required)"
  type        = string
}

variable "maintenance_configuration_id" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_maintenance_assignment_virtual_machine" "this" {
  # location - (required) is a type of string
  location = var.location
  # maintenance_configuration_id - (required) is a type of string
  maintenance_configuration_id = var.maintenance_configuration_id
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = var.virtual_machine_id

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
  value       = azurerm_maintenance_assignment_virtual_machine.this.id
}

output "this" {
  value = azurerm_maintenance_assignment_virtual_machine.this
}
```

[top](#index)