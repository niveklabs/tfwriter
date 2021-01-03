# azurerm_api_management_diagnostic

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
module "azurerm_api_management_diagnostic" {
  source = "./modules/azurerm/r/azurerm_api_management_diagnostic"

  # api_management_logger_id - (required) is a type of string
  api_management_logger_id = null
  # api_management_name - (required) is a type of string
  api_management_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # identifier - (required) is a type of string
  identifier = null
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
variable "api_management_logger_id" {
  description = "(required)"
  type        = string
}

variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identifier" {
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
resource "azurerm_api_management_diagnostic" "this" {
  api_management_logger_id = var.api_management_logger_id
  api_management_name      = var.api_management_name
  enabled                  = var.enabled
  identifier               = var.identifier
  resource_group_name      = var.resource_group_name

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
  value       = azurerm_api_management_diagnostic.this.id
}

output "this" {
  value = azurerm_api_management_diagnostic.this
}
```

[top](#index)