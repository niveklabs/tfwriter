# azurerm_automation_variable_bool

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_automation_variable_bool" {
  source = "./modules/azurerm/d/azurerm_automation_variable_bool"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
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
data "azurerm_automation_variable_bool" "this" {
  # automation_account_name - (required) is a type of string
  automation_account_name = var.automation_account_name
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.azurerm_automation_variable_bool.this.description
}

output "encrypted" {
  description = "returns a bool"
  value       = data.azurerm_automation_variable_bool.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_automation_variable_bool.this.id
}

output "value" {
  description = "returns a bool"
  value       = data.azurerm_automation_variable_bool.this.value
}

output "this" {
  value = azurerm_automation_variable_bool.this
}
```

[top](#index)