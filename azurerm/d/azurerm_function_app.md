# azurerm_function_app

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_function_app" {
  source = "./modules/azurerm/d/azurerm_function_app"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_function_app" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

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
output "app_service_plan_id" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.app_service_plan_id
}

output "app_settings" {
  description = "returns a map of string"
  value       = data.azurerm_function_app.this.app_settings
}

output "connection_string" {
  description = "returns a list of object"
  value       = data.azurerm_function_app.this.connection_string
}

output "custom_domain_verification_id" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.custom_domain_verification_id
}

output "default_hostname" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.default_hostname
}

output "enabled" {
  description = "returns a bool"
  value       = data.azurerm_function_app.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_function_app.this.identity
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.location
}

output "os_type" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.os_type
}

output "outbound_ip_addresses" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.outbound_ip_addresses
}

output "possible_outbound_ip_addresses" {
  description = "returns a string"
  value       = data.azurerm_function_app.this.possible_outbound_ip_addresses
}

output "site_config" {
  description = "returns a list of object"
  value       = data.azurerm_function_app.this.site_config
}

output "site_credential" {
  description = "returns a list of object"
  value       = data.azurerm_function_app.this.site_credential
}

output "source_control" {
  description = "returns a list of object"
  value       = data.azurerm_function_app.this.source_control
}

output "this" {
  value = azurerm_function_app.this
}
```

[top](#index)