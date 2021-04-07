# azurerm_network_interface_backend_address_pool_association

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
module "azurerm_network_interface_backend_address_pool_association" {
  source = "./modules/azurerm/r/azurerm_network_interface_backend_address_pool_association"

  # backend_address_pool_id - (required) is a type of string
  backend_address_pool_id = null
  # ip_configuration_name - (required) is a type of string
  ip_configuration_name = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null

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
variable "backend_address_pool_id" {
  description = "(required)"
  type        = string
}

variable "ip_configuration_name" {
  description = "(required)"
  type        = string
}

variable "network_interface_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_network_interface_backend_address_pool_association" "this" {
  # backend_address_pool_id - (required) is a type of string
  backend_address_pool_id = var.backend_address_pool_id
  # ip_configuration_name - (required) is a type of string
  ip_configuration_name = var.ip_configuration_name
  # network_interface_id - (required) is a type of string
  network_interface_id = var.network_interface_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azurerm_network_interface_backend_address_pool_association.this.id
}

output "this" {
  value = azurerm_network_interface_backend_address_pool_association.this
}
```

[top](#index)