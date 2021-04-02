# azurerm_function_app_host_keys

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
module "azurerm_function_app_host_keys" {
  source = "./modules/azurerm/d/azurerm_function_app_host_keys"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
data "azurerm_function_app_host_keys" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "default_function_key" {
  description = "returns a string"
  value       = data.azurerm_function_app_host_keys.this.default_function_key
  sensitive   = true
}

output "event_grid_extension_config_key" {
  description = "returns a string"
  value       = data.azurerm_function_app_host_keys.this.event_grid_extension_config_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_function_app_host_keys.this.id
}

output "master_key" {
  description = "returns a string"
  value       = data.azurerm_function_app_host_keys.this.master_key
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = data.azurerm_function_app_host_keys.this.primary_key
  sensitive   = true
}

output "this" {
  value = azurerm_function_app_host_keys.this
}
```

[top](#index)