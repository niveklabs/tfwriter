# azurerm_private_dns_zone

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
module "azurerm_private_dns_zone" {
  source = "./modules/azurerm/d/azurerm_private_dns_zone"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (optional) is a type of string
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
  description = "(optional)"
  type        = string
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
data "azurerm_private_dns_zone" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_private_dns_zone.this.id
}

output "max_number_of_record_sets" {
  description = "returns a number"
  value       = data.azurerm_private_dns_zone.this.max_number_of_record_sets
}

output "max_number_of_virtual_network_links" {
  description = "returns a number"
  value       = data.azurerm_private_dns_zone.this.max_number_of_virtual_network_links
}

output "max_number_of_virtual_network_links_with_registration" {
  description = "returns a number"
  value       = data.azurerm_private_dns_zone.this.max_number_of_virtual_network_links_with_registration
}

output "number_of_record_sets" {
  description = "returns a number"
  value       = data.azurerm_private_dns_zone.this.number_of_record_sets
}

output "resource_group_name" {
  description = "returns a string"
  value       = data.azurerm_private_dns_zone.this.resource_group_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_private_dns_zone.this.tags
}

output "this" {
  value = azurerm_private_dns_zone.this
}
```

[top](#index)