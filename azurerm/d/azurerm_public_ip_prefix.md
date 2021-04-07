# azurerm_public_ip_prefix

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
module "azurerm_public_ip_prefix" {
  source = "./modules/azurerm/d/azurerm_public_ip_prefix"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # zones - (optional) is a type of list of string
  zones = []

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

variable "zones" {
  description = "(optional)"
  type        = list(string)
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
data "azurerm_public_ip_prefix" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # zones - (optional) is a type of list of string
  zones = var.zones

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_public_ip_prefix.this.id
}

output "ip_prefix" {
  description = "returns a string"
  value       = data.azurerm_public_ip_prefix.this.ip_prefix
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_public_ip_prefix.this.location
}

output "prefix_length" {
  description = "returns a number"
  value       = data.azurerm_public_ip_prefix.this.prefix_length
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_public_ip_prefix.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_public_ip_prefix.this.tags
}

output "zones" {
  description = "returns a list of string"
  value       = data.azurerm_public_ip_prefix.this.zones
}

output "this" {
  value = azurerm_public_ip_prefix.this
}
```

[top](#index)