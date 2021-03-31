# azurerm_lb

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_lb" {
  source = "./modules/azurerm/d/azurerm_lb"

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
data "azurerm_lb" "this" {
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
output "frontend_ip_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_lb.this.frontend_ip_configuration
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_lb.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_lb.this.location
}

output "private_ip_address" {
  description = "returns a string"
  value       = data.azurerm_lb.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_lb.this.private_ip_addresses
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_lb.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_lb.this.tags
}

output "this" {
  value = azurerm_lb.this
}
```

[top](#index)