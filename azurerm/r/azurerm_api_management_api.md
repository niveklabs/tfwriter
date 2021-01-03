# azurerm_api_management_api

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
module "azurerm_api_management_api" {
  source = "./modules/azurerm/r/azurerm_api_management_api"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
  # path - (required) is a type of string
  path = null
  # protocols - (required) is a type of set of string
  protocols = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # revision - (required) is a type of string
  revision = null
  # service_url - (optional) is a type of string
  service_url = null
  # soap_pass_through - (optional) is a type of bool
  soap_pass_through = null
  # subscription_required - (optional) is a type of bool
  subscription_required = null
  # version - (optional) is a type of string
  version = null
  # version_set_id - (optional) is a type of string
  version_set_id = null

  import = [{
    content_format = null
    content_value  = null
    wsdl_selector = [{
      endpoint_name = null
      service_name  = null
    }]
  }]

  oauth2_authorization = [{
    authorization_server_name = null
    scope                     = null
  }]

  openid_authentication = [{
    bearer_token_sending_methods = []
    openid_provider_name         = null
  }]

  subscription_key_parameter_names = [{
    header = null
    query  = null
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
variable "api_management_name" {
  description = "(required)"
  type        = string
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "protocols" {
  description = "(required)"
  type        = set(string)
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "revision" {
  description = "(required)"
  type        = string
}

variable "service_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "soap_pass_through" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "subscription_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_format = string
      content_value  = string
      wsdl_selector = list(object(
        {
          endpoint_name = string
          service_name  = string
        }
      ))
    }
  ))
  default = []
}

variable "oauth2_authorization" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authorization_server_name = string
      scope                     = string
    }
  ))
  default = []
}

variable "openid_authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bearer_token_sending_methods = set(string)
      openid_provider_name         = string
    }
  ))
  default = []
}

variable "subscription_key_parameter_names" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      header = string
      query  = string
    }
  ))
  default = []
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
resource "azurerm_api_management_api" "this" {
  api_management_name   = var.api_management_name
  description           = var.description
  display_name          = var.display_name
  name                  = var.name
  path                  = var.path
  protocols             = var.protocols
  resource_group_name   = var.resource_group_name
  revision              = var.revision
  service_url           = var.service_url
  soap_pass_through     = var.soap_pass_through
  subscription_required = var.subscription_required
  version               = var.version
  version_set_id        = var.version_set_id

  dynamic "import" {
    for_each = var.import
    content {
      content_format = import.value["content_format"]
      content_value  = import.value["content_value"]

      dynamic "wsdl_selector" {
        for_each = import.value.wsdl_selector
        content {
          endpoint_name = wsdl_selector.value["endpoint_name"]
          service_name  = wsdl_selector.value["service_name"]
        }
      }

    }
  }

  dynamic "oauth2_authorization" {
    for_each = var.oauth2_authorization
    content {
      authorization_server_name = oauth2_authorization.value["authorization_server_name"]
      scope                     = oauth2_authorization.value["scope"]
    }
  }

  dynamic "openid_authentication" {
    for_each = var.openid_authentication
    content {
      bearer_token_sending_methods = openid_authentication.value["bearer_token_sending_methods"]
      openid_provider_name         = openid_authentication.value["openid_provider_name"]
    }
  }

  dynamic "subscription_key_parameter_names" {
    for_each = var.subscription_key_parameter_names
    content {
      header = subscription_key_parameter_names.value["header"]
      query  = subscription_key_parameter_names.value["query"]
    }
  }

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
  value       = azurerm_api_management_api.this.id
}

output "is_current" {
  description = "returns a bool"
  value       = azurerm_api_management_api.this.is_current
}

output "is_online" {
  description = "returns a bool"
  value       = azurerm_api_management_api.this.is_online
}

output "service_url" {
  description = "returns a string"
  value       = azurerm_api_management_api.this.service_url
}

output "version" {
  description = "returns a string"
  value       = azurerm_api_management_api.this.version
}

output "version_set_id" {
  description = "returns a string"
  value       = azurerm_api_management_api.this.version_set_id
}

output "this" {
  value = azurerm_api_management_api.this
}
```

[top](#index)