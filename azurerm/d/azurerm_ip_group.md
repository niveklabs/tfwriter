# azurerm_ip_group

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
module "azurerm_ip_group" {
  source = "./modules/azurerm/d/azurerm_ip_group"

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
data "azurerm_ip_group" "this" {
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
output "cidrs" {
  description = "returns a set of string"
  value       = data.azurerm_ip_group.this.cidrs
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_ip_group.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_ip_group.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_ip_group.this.tags
}

output "this" {
  value = azurerm_ip_group.this
}
```

[top](#index)