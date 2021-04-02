# azurerm_redis_linked_server

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
module "azurerm_redis_linked_server" {
  source = "./modules/azurerm/r/azurerm_redis_linked_server"

  # linked_redis_cache_id - (required) is a type of string
  linked_redis_cache_id = null
  # linked_redis_cache_location - (required) is a type of string
  linked_redis_cache_location = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server_role - (required) is a type of string
  server_role = null
  # target_redis_cache_name - (required) is a type of string
  target_redis_cache_name = null

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
variable "linked_redis_cache_id" {
  description = "(required)"
  type        = string
}

variable "linked_redis_cache_location" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "server_role" {
  description = "(required)"
  type        = string
}

variable "target_redis_cache_name" {
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
resource "azurerm_redis_linked_server" "this" {
  linked_redis_cache_id       = var.linked_redis_cache_id
  linked_redis_cache_location = var.linked_redis_cache_location
  resource_group_name         = var.resource_group_name
  server_role                 = var.server_role
  target_redis_cache_name     = var.target_redis_cache_name

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
  value       = azurerm_redis_linked_server.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_redis_linked_server.this.name
}

output "this" {
  value = azurerm_redis_linked_server.this
}
```

[top](#index)