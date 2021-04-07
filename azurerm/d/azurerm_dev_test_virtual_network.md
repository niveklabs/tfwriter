# azurerm_dev_test_virtual_network

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
module "azurerm_dev_test_virtual_network" {
  source = "./modules/azurerm/d/azurerm_dev_test_virtual_network"

  # lab_name - (required) is a type of string
  lab_name = null
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
variable "lab_name" {
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
data "azurerm_dev_test_virtual_network" "this" {
  # lab_name - (required) is a type of string
  lab_name = var.lab_name
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
output "allowed_subnets" {
  description = "returns a list of object"
  value       = data.azurerm_dev_test_virtual_network.this.allowed_subnets
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_virtual_network.this.id
}

output "subnet_overrides" {
  description = "returns a list of object"
  value       = data.azurerm_dev_test_virtual_network.this.subnet_overrides
}

output "unique_identifier" {
  description = "returns a string"
  value       = data.azurerm_dev_test_virtual_network.this.unique_identifier
}

output "this" {
  value = azurerm_dev_test_virtual_network.this
}
```

[top](#index)