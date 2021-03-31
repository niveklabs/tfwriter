# azurerm_network_profile

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_network_profile" {
  source = "./modules/azurerm/r/azurerm_network_profile"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  container_network_interface = [{
    ip_configuration = [{
      name      = null
      subnet_id = null
    }]
    name = null
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
variable "location" {
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

variable "container_network_interface" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      ip_configuration = list(object(
        {
          name      = string
          subnet_id = string
        }
      ))
      name = string
    }
  ))
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
resource "azurerm_network_profile" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "container_network_interface" {
    for_each = var.container_network_interface
    content {
      name = container_network_interface.value["name"]

      dynamic "ip_configuration" {
        for_each = container_network_interface.value.ip_configuration
        content {
          name      = ip_configuration.value["name"]
          subnet_id = ip_configuration.value["subnet_id"]
        }
      }

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
output "container_network_interface_ids" {
  description = "returns a list of string"
  value       = azurerm_network_profile.this.container_network_interface_ids
}

output "id" {
  description = "returns a string"
  value       = azurerm_network_profile.this.id
}

output "this" {
  value = azurerm_network_profile.this
}
```

[top](#index)