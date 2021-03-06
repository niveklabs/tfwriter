# azurerm_automation_dsc_configuration

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
module "azurerm_automation_dsc_configuration" {
  source = "./modules/azurerm/r/azurerm_automation_dsc_configuration"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # content_embedded - (required) is a type of string
  content_embedded = null
  # description - (optional) is a type of string
  description = null
  # location - (required) is a type of string
  location = null
  # log_verbose - (optional) is a type of bool
  log_verbose = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "log_verbose" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_automation_dsc_configuration" "this" {
  # automation_account_name - (required) is a type of string
  automation_account_name = var.automation_account_name
  # content_embedded - (required) is a type of string
  content_embedded = var.content_embedded
  # description - (optional) is a type of string
  description = var.description
  # location - (required) is a type of string
  location = var.location
  # log_verbose - (optional) is a type of bool
  log_verbose = var.log_verbose
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = azurerm_automation_dsc_configuration.this.id
}

output "state" {
  description = "returns a string"
  value       = azurerm_automation_dsc_configuration.this.state
}

output "this" {
  value = azurerm_automation_dsc_configuration.this
}
```

[top](#index)