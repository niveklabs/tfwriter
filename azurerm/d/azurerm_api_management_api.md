# azurerm_api_management_api

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_api_management_api" {
  source = "./modules/azurerm/d/azurerm_api_management_api"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # revision - (required) is a type of string
  revision = null

  timeouts = [{
    read = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "revision" {
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
data "azurerm_api_management_api" "this" {
  api_management_name = var.api_management_name
  name                = var.name
  resource_group_name = var.resource_group_name
  revision            = var.revision

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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
  value       = data.azurerm_api_management_api.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_api.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_api_management_api.this.id
}

output "is_current" {
  description = "returns a bool"
  value       = data.azurerm_api_management_api.this.is_current
}

output "is_online" {
  description = "returns a bool"
  value       = data.azurerm_api_management_api.this.is_online
}

output "path" {
  description = "returns a string"
  value       = data.azurerm_api_management_api.this.path
}

output "protocols" {
  description = "returns a list of string"
  value       = data.azurerm_api_management_api.this.protocols
}

output "service_url" {
  description = "returns a string"
  value       = data.azurerm_api_management_api.this.service_url
}

output "soap_pass_through" {
  description = "returns a bool"
  value       = data.azurerm_api_management_api.this.soap_pass_through
}

output "subscription_key_parameter_names" {
  description = "returns a list of object"
  value       = data.azurerm_api_management_api.this.subscription_key_parameter_names
}

output "subscription_required" {
  description = "returns a bool"
  value       = data.azurerm_api_management_api.this.subscription_required
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_api_management_api.this.version
}

output "version_set_id" {
  description = "returns a string"
  value       = data.azurerm_api_management_api.this.version_set_id
}

output "this" {
  value = azurerm_api_management_api.this
}
```

[top](#index)