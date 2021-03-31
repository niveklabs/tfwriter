# azurerm_api_management_authorization_server

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
module "azurerm_api_management_authorization_server" {
  source = "./modules/azurerm/r/azurerm_api_management_authorization_server"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # authorization_endpoint - (required) is a type of string
  authorization_endpoint = null
  # authorization_methods - (required) is a type of set of string
  authorization_methods = []
  # bearer_token_sending_methods - (optional) is a type of set of string
  bearer_token_sending_methods = []
  # client_authentication_method - (optional) is a type of set of string
  client_authentication_method = []
  # client_id - (required) is a type of string
  client_id = null
  # client_registration_endpoint - (required) is a type of string
  client_registration_endpoint = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # default_scope - (optional) is a type of string
  default_scope = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # grant_types - (required) is a type of set of string
  grant_types = []
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # resource_owner_password - (optional) is a type of string
  resource_owner_password = null
  # resource_owner_username - (optional) is a type of string
  resource_owner_username = null
  # support_state - (optional) is a type of bool
  support_state = null
  # token_endpoint - (optional) is a type of string
  token_endpoint = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  token_body_parameter = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "authorization_endpoint" {
  description = "(required)"
  type        = string
}

variable "authorization_methods" {
  description = "(required)"
  type        = set(string)
}

variable "bearer_token_sending_methods" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "client_authentication_method" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_registration_endpoint" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "grant_types" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "resource_owner_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_owner_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "support_state" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "token_endpoint" {
  description = "(optional)"
  type        = string
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

variable "token_body_parameter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_api_management_authorization_server" "this" {
  api_management_name          = var.api_management_name
  authorization_endpoint       = var.authorization_endpoint
  authorization_methods        = var.authorization_methods
  bearer_token_sending_methods = var.bearer_token_sending_methods
  client_authentication_method = var.client_authentication_method
  client_id                    = var.client_id
  client_registration_endpoint = var.client_registration_endpoint
  client_secret                = var.client_secret
  default_scope                = var.default_scope
  description                  = var.description
  display_name                 = var.display_name
  grant_types                  = var.grant_types
  name                         = var.name
  resource_group_name          = var.resource_group_name
  resource_owner_password      = var.resource_owner_password
  resource_owner_username      = var.resource_owner_username
  support_state                = var.support_state
  token_endpoint               = var.token_endpoint

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

  dynamic "token_body_parameter" {
    for_each = var.token_body_parameter
    content {
      name  = token_body_parameter.value["name"]
      value = token_body_parameter.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_api_management_authorization_server.this.id
}

output "this" {
  value = azurerm_api_management_authorization_server.this
}
```

[top](#index)