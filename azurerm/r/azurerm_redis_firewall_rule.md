# azurerm_redis_firewall_rule

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
module "azurerm_redis_firewall_rule" {
  source = "./modules/azurerm/r/azurerm_redis_firewall_rule"

  # end_ip - (required) is a type of string
  end_ip = null
  # name - (required) is a type of string
  name = null
  # redis_cache_name - (required) is a type of string
  redis_cache_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # start_ip - (required) is a type of string
  start_ip = null

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
variable "end_ip" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "redis_cache_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "start_ip" {
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
resource "azurerm_redis_firewall_rule" "this" {
  end_ip              = var.end_ip
  name                = var.name
  redis_cache_name    = var.redis_cache_name
  resource_group_name = var.resource_group_name
  start_ip            = var.start_ip

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
  value       = azurerm_redis_firewall_rule.this.id
}

output "this" {
  value = azurerm_redis_firewall_rule.this
}
```

[top](#index)