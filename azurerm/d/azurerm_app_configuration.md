# azurerm_app_configuration

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
module "azurerm_app_configuration" {
  source = "./modules/azurerm/d/azurerm_app_configuration"

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
data "azurerm_app_configuration" "this" {
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
output "endpoint" {
  description = "returns a string"
  value       = data.azurerm_app_configuration.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_app_configuration.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_app_configuration.this.location
}

output "primary_read_key" {
  description = "returns a list of object"
  value       = data.azurerm_app_configuration.this.primary_read_key
}

output "primary_write_key" {
  description = "returns a list of object"
  value       = data.azurerm_app_configuration.this.primary_write_key
}

output "secondary_read_key" {
  description = "returns a list of object"
  value       = data.azurerm_app_configuration.this.secondary_read_key
}

output "secondary_write_key" {
  description = "returns a list of object"
  value       = data.azurerm_app_configuration.this.secondary_write_key
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_app_configuration.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_app_configuration.this.tags
}

output "this" {
  value = azurerm_app_configuration.this
}
```

[top](#index)