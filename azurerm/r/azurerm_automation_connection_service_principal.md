# azurerm_automation_connection_service_principal

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
module "azurerm_automation_connection_service_principal" {
  source = "./modules/azurerm/r/azurerm_automation_connection_service_principal"

  # application_id - (required) is a type of string
  application_id = null
  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # certificate_thumbprint - (required) is a type of string
  certificate_thumbprint = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # subscription_id - (required) is a type of string
  subscription_id = null
  # tenant_id - (required) is a type of string
  tenant_id = null

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
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "automation_account_name" {
  description = "(required)"
  type        = string
}

variable "certificate_thumbprint" {
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

variable "subscription_id" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
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
resource "azurerm_automation_connection_service_principal" "this" {
  application_id          = var.application_id
  automation_account_name = var.automation_account_name
  certificate_thumbprint  = var.certificate_thumbprint
  description             = var.description
  name                    = var.name
  resource_group_name     = var.resource_group_name
  subscription_id         = var.subscription_id
  tenant_id               = var.tenant_id

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
  value       = azurerm_automation_connection_service_principal.this.id
}

output "this" {
  value = azurerm_automation_connection_service_principal.this
}
```

[top](#index)