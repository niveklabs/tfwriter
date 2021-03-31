# azurerm_api_management_identity_provider_aadb2c

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
module "azurerm_api_management_identity_provider_aadb2c" {
  source = "./modules/azurerm/r/azurerm_api_management_identity_provider_aadb2c"

  # allowed_tenant - (required) is a type of string
  allowed_tenant = null
  # api_management_name - (required) is a type of string
  api_management_name = null
  # authority - (required) is a type of string
  authority = null
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # password_reset_policy - (optional) is a type of string
  password_reset_policy = null
  # profile_editing_policy - (optional) is a type of string
  profile_editing_policy = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # signin_policy - (required) is a type of string
  signin_policy = null
  # signin_tenant - (required) is a type of string
  signin_tenant = null
  # signup_policy - (required) is a type of string
  signup_policy = null

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
variable "allowed_tenant" {
  description = "(required)"
  type        = string
}

variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "authority" {
  description = "(required)"
  type        = string
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(required)"
  type        = string
}

variable "password_reset_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_editing_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "signin_policy" {
  description = "(required)"
  type        = string
}

variable "signin_tenant" {
  description = "(required)"
  type        = string
}

variable "signup_policy" {
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
resource "azurerm_api_management_identity_provider_aadb2c" "this" {
  allowed_tenant         = var.allowed_tenant
  api_management_name    = var.api_management_name
  authority              = var.authority
  client_id              = var.client_id
  client_secret          = var.client_secret
  password_reset_policy  = var.password_reset_policy
  profile_editing_policy = var.profile_editing_policy
  resource_group_name    = var.resource_group_name
  signin_policy          = var.signin_policy
  signin_tenant          = var.signin_tenant
  signup_policy          = var.signup_policy

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
  value       = azurerm_api_management_identity_provider_aadb2c.this.id
}

output "this" {
  value = azurerm_api_management_identity_provider_aadb2c.this
}
```

[top](#index)