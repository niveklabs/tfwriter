# azurerm_automation_dsc_nodeconfiguration

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
module "azurerm_automation_dsc_nodeconfiguration" {
  source = "./modules/azurerm/r/azurerm_automation_dsc_nodeconfiguration"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # content_embedded - (required) is a type of string
  content_embedded = null
  # name - (required) is a type of string
  name = null
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
variable "automation_account_name" {
  description = "(required)"
  type        = string
}

variable "content_embedded" {
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
resource "azurerm_automation_dsc_nodeconfiguration" "this" {
  automation_account_name = var.automation_account_name
  content_embedded        = var.content_embedded
  name                    = var.name
  resource_group_name     = var.resource_group_name

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
output "configuration_name" {
  description = "returns a string"
  value       = azurerm_automation_dsc_nodeconfiguration.this.configuration_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_automation_dsc_nodeconfiguration.this.id
}

output "this" {
  value = azurerm_automation_dsc_nodeconfiguration.this
}
```

[top](#index)