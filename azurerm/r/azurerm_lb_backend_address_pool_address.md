# azurerm_lb_backend_address_pool_address

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
module "azurerm_lb_backend_address_pool_address" {
  source = "./modules/azurerm/r/azurerm_lb_backend_address_pool_address"

  # backend_address_pool_id - (required) is a type of string
  backend_address_pool_id = null
  # ip_address - (required) is a type of string
  ip_address = null
  # name - (required) is a type of string
  name = null
  # virtual_network_id - (required) is a type of string
  virtual_network_id = null

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

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "virtual_network_id" {
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
resource "azurerm_lb_backend_address_pool_address" "this" {
  # backend_address_pool_id - (required) is a type of string
  backend_address_pool_id = var.backend_address_pool_id
  # ip_address - (required) is a type of string
  ip_address = var.ip_address
  # name - (required) is a type of string
  name = var.name
  # virtual_network_id - (required) is a type of string
  virtual_network_id = var.virtual_network_id

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
  value       = azurerm_lb_backend_address_pool_address.this.id
}

output "this" {
  value = azurerm_lb_backend_address_pool_address.this
}
```

[top](#index)