# azurerm_dev_test_virtual_network

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/azurerm/r/azurerm_dev_test_virtual_network"

  # description - (optional) is a type of string
  description = null
  # lab_name - (required) is a type of string
  lab_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  subnet = [{
    name                            = null
    use_in_virtual_machine_creation = null
    use_public_ip_address           = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "subnet" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name                            = string
      use_in_virtual_machine_creation = string
      use_public_ip_address           = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_dev_test_virtual_network" "this" {
  description         = var.description
  lab_name            = var.lab_name
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "subnet" {
    for_each = var.subnet
    content {
      use_in_virtual_machine_creation = subnet.value["use_in_virtual_machine_creation"]
      use_public_ip_address           = subnet.value["use_public_ip_address"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_dev_test_virtual_network.this.id
}

output "unique_identifier" {
  description = "returns a string"
  value       = azurerm_dev_test_virtual_network.this.unique_identifier
}

output "this" {
  value = azurerm_dev_test_virtual_network.this
}
```

[top](#index)