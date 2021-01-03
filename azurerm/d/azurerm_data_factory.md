# azurerm_data_factory

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
module "azurerm_data_factory" {
  source = "./modules/azurerm/d/azurerm_data_factory"

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
data "azurerm_data_factory" "this" {
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
output "github_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_data_factory.this.github_configuration
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_factory.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_data_factory.this.identity
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_data_factory.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_data_factory.this.tags
}

output "vsts_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_data_factory.this.vsts_configuration
}

output "this" {
  value = azurerm_data_factory.this
}
```

[top](#index)