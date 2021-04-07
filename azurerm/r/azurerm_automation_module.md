# azurerm_automation_module

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
module "azurerm_automation_module" {
  source = "./modules/azurerm/r/azurerm_automation_module"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  module_link = [{
    hash = [{
      algorithm = null
      value     = null
    }]
    uri = null
  }]

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
variable "automation_account_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "module_link" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      hash = list(object(
        {
          algorithm = string
          value     = string
        }
      ))
      uri = string
    }
  ))
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
resource "azurerm_automation_module" "this" {
  # automation_account_name - (required) is a type of string
  automation_account_name = var.automation_account_name
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "module_link" {
    for_each = var.module_link
    content {
      # uri - (required) is a type of string
      uri = module_link.value["uri"]

      dynamic "hash" {
        for_each = module_link.value.hash
        content {
          # algorithm - (required) is a type of string
          algorithm = hash.value["algorithm"]
          # value - (required) is a type of string
          value = hash.value["value"]
        }
      }

    }
  }

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
  value       = azurerm_automation_module.this.id
}

output "this" {
  value = azurerm_automation_module.this
}
```

[top](#index)