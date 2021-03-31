# azurerm_api_management_openid_connect_provider

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
module "azurerm_api_management_openid_connect_provider" {
  source = "./modules/azurerm/r/azurerm_api_management_openid_connect_provider"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # metadata_endpoint - (required) is a type of string
  metadata_endpoint = null
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
variable "api_management_name" {
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "metadata_endpoint" {
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
resource "azurerm_api_management_openid_connect_provider" "this" {
  api_management_name = var.api_management_name
  client_id           = var.client_id
  client_secret       = var.client_secret
  description         = var.description
  display_name        = var.display_name
  metadata_endpoint   = var.metadata_endpoint
  name                = var.name
  resource_group_name = var.resource_group_name

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
  value       = azurerm_api_management_openid_connect_provider.this.id
}

output "this" {
  value = azurerm_api_management_openid_connect_provider.this
}
```

[top](#index)