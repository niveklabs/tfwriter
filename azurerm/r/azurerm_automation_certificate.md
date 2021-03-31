# azurerm_automation_certificate

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
module "azurerm_automation_certificate" {
  source = "./modules/azurerm/r/azurerm_automation_certificate"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # base64 - (required) is a type of string
  base64 = null
  # description - (optional) is a type of string
  description = null
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

variable "base64" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
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
resource "azurerm_automation_certificate" "this" {
  automation_account_name = var.automation_account_name
  base64                  = var.base64
  description             = var.description
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
output "exportable" {
  description = "returns a bool"
  value       = azurerm_automation_certificate.this.exportable
}

output "id" {
  description = "returns a string"
  value       = azurerm_automation_certificate.this.id
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_automation_certificate.this.thumbprint
}

output "this" {
  value = azurerm_automation_certificate.this
}
```

[top](#index)