# azurerm_traffic_manager_profile

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
module "azurerm_traffic_manager_profile" {
  source = "./modules/azurerm/r/azurerm_traffic_manager_profile"

  # max_return - (optional) is a type of number
  max_return = null
  # name - (required) is a type of string
  name = null
  # profile_status - (optional) is a type of string
  profile_status = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # traffic_routing_method - (required) is a type of string
  traffic_routing_method = null
  # traffic_view_enabled - (optional) is a type of bool
  traffic_view_enabled = null

  dns_config = [{
    relative_name = null
    ttl           = null
  }]

  monitor_config = [{
    custom_header = [{
      name  = null
      value = null
    }]
    expected_status_code_ranges  = []
    interval_in_seconds          = null
    path                         = null
    port                         = null
    protocol                     = null
    timeout_in_seconds           = null
    tolerated_number_of_failures = null
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
variable "max_return" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "profile_status" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "traffic_routing_method" {
  description = "(required)"
  type        = string
}

variable "traffic_view_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dns_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      relative_name = string
      ttl           = number
    }
  ))
}

variable "monitor_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      custom_header = list(object(
        {
          name  = string
          value = string
        }
      ))
      expected_status_code_ranges  = list(string)
      interval_in_seconds          = number
      path                         = string
      port                         = number
      protocol                     = string
      timeout_in_seconds           = number
      tolerated_number_of_failures = number
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
resource "azurerm_traffic_manager_profile" "this" {
  max_return             = var.max_return
  name                   = var.name
  profile_status         = var.profile_status
  resource_group_name    = var.resource_group_name
  tags                   = var.tags
  traffic_routing_method = var.traffic_routing_method
  traffic_view_enabled   = var.traffic_view_enabled

  dynamic "dns_config" {
    for_each = var.dns_config
    content {
      relative_name = dns_config.value["relative_name"]
      ttl           = dns_config.value["ttl"]
    }
  }

  dynamic "monitor_config" {
    for_each = var.monitor_config
    content {
      expected_status_code_ranges  = monitor_config.value["expected_status_code_ranges"]
      interval_in_seconds          = monitor_config.value["interval_in_seconds"]
      path                         = monitor_config.value["path"]
      port                         = monitor_config.value["port"]
      protocol                     = monitor_config.value["protocol"]
      timeout_in_seconds           = monitor_config.value["timeout_in_seconds"]
      tolerated_number_of_failures = monitor_config.value["tolerated_number_of_failures"]

      dynamic "custom_header" {
        for_each = monitor_config.value.custom_header
        content {
          name  = custom_header.value["name"]
          value = custom_header.value["value"]
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
output "fqdn" {
  description = "returns a string"
  value       = azurerm_traffic_manager_profile.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_traffic_manager_profile.this.id
}

output "profile_status" {
  description = "returns a string"
  value       = azurerm_traffic_manager_profile.this.profile_status
}

output "this" {
  value = azurerm_traffic_manager_profile.this
}
```

[top](#index)