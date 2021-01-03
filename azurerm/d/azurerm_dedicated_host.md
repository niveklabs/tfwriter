# azurerm_dedicated_host

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
module "azurerm_dedicated_host" {
  source = "./modules/azurerm/d/azurerm_dedicated_host"

  # dedicated_host_group_name - (required) is a type of string
  dedicated_host_group_name = null
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
variable "dedicated_host_group_name" {
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
data "azurerm_dedicated_host" "this" {
  dedicated_host_group_name = var.dedicated_host_group_name
  name                      = var.name
  resource_group_name       = var.resource_group_name

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
  value       = data.azurerm_dedicated_host.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_dedicated_host.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_dedicated_host.this.tags
}

output "this" {
  value = azurerm_dedicated_host.this
}
```

[top](#index)