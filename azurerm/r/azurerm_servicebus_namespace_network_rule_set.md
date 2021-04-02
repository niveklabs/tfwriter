# azurerm_servicebus_namespace_network_rule_set

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
module "azurerm_servicebus_namespace_network_rule_set" {
  source = "./modules/azurerm/r/azurerm_servicebus_namespace_network_rule_set"

  # default_action - (optional) is a type of string
  default_action = null
  # ip_rules - (optional) is a type of set of string
  ip_rules = []
  # namespace_name - (required) is a type of string
  namespace_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  network_rules = [{
    ignore_missing_vnet_service_endpoint = null
    subnet_id                            = null
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
variable "default_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_rules" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "network_rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ignore_missing_vnet_service_endpoint = bool
      subnet_id                            = string
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
resource "azurerm_servicebus_namespace_network_rule_set" "this" {
  default_action      = var.default_action
  ip_rules            = var.ip_rules
  namespace_name      = var.namespace_name
  resource_group_name = var.resource_group_name

  dynamic "network_rules" {
    for_each = var.network_rules
    content {
      ignore_missing_vnet_service_endpoint = network_rules.value["ignore_missing_vnet_service_endpoint"]
      subnet_id                            = network_rules.value["subnet_id"]
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
  value       = azurerm_servicebus_namespace_network_rule_set.this.id
}

output "this" {
  value = azurerm_servicebus_namespace_network_rule_set.this
}
```

[top](#index)