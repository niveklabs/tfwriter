# azurerm_netapp_pool

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
module "azurerm_netapp_pool" {
  source = "./modules/azurerm/d/azurerm_netapp_pool"

  # account_name - (required) is a type of string
  account_name = null
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
variable "account_name" {
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_netapp_pool" "this" {
  account_name        = var.account_name
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
  value       = data.azurerm_netapp_pool.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_netapp_pool.this.location
}

output "service_level" {
  description = "returns a string"
  value       = data.azurerm_netapp_pool.this.service_level
}

output "size_in_tb" {
  description = "returns a number"
  value       = data.azurerm_netapp_pool.this.size_in_tb
}

output "this" {
  value = azurerm_netapp_pool.this
}
```

[top](#index)