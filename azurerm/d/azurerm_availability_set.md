# azurerm_availability_set

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
module "azurerm_availability_set" {
  source = "./modules/azurerm/d/azurerm_availability_set"

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
data "azurerm_availability_set" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
  value       = data.azurerm_availability_set.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_availability_set.this.location
}

output "managed" {
  description = "returns a bool"
  value       = data.azurerm_availability_set.this.managed
}

output "platform_fault_domain_count" {
  description = "returns a string"
  value       = data.azurerm_availability_set.this.platform_fault_domain_count
}

output "platform_update_domain_count" {
  description = "returns a string"
  value       = data.azurerm_availability_set.this.platform_update_domain_count
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_availability_set.this.tags
}

output "this" {
  value = azurerm_availability_set.this
}
```

[top](#index)