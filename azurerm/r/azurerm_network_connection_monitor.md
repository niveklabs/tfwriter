# azurerm_network_connection_monitor

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_network_connection_monitor" {
  source = [{
    port               = null
    virtual_machine_id = null
  }]

  # auto_start - (optional) is a type of bool
  auto_start = null
  # interval_in_seconds - (optional) is a type of number
  interval_in_seconds = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_watcher_id - (required) is a type of string
  network_watcher_id = null
  # notes - (optional) is a type of string
  notes = null
  # output_workspace_resource_ids - (optional) is a type of set of string
  output_workspace_resource_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  destination = [{
    address            = null
    port               = null
    virtual_machine_id = null
  }]

  endpoint = [{
    address = null
    filter = [{
      item = [{
        address = null
        type    = null
      }]
      type = null
    }]
    name               = null
    virtual_machine_id = null
  }]


  test_configuration = [{
    http_configuration = [{
      method       = null
      path         = null
      port         = null
      prefer_https = null
      request_header = [{
        name  = null
        value = null
      }]
      valid_status_code_ranges = []
    }]
    icmp_configuration = [{
      trace_route_enabled = null
    }]
    name                 = null
    preferred_ip_version = null
    protocol             = null
    success_threshold = [{
      checks_failed_percent = null
      round_trip_time_ms    = null
    }]
    tcp_configuration = [{
      port                = null
      trace_route_enabled = null
    }]
    test_frequency_in_seconds = null
  }]

  test_group = [{
    destination_endpoints    = []
    enabled                  = null
    name                     = null
    source_endpoints         = []
    test_configuration_names = []
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
variable "auto_start" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interval_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_watcher_id" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_workspace_resource_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "destination" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address            = string
      port               = number
      virtual_machine_id = string
    }
  ))
  default = []
}

variable "endpoint" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      address = string
      filter = list(object(
        {
          item = set(object(
            {
              address = string
              type    = string
            }
          ))
          type = string
        }
      ))
      name               = string
      virtual_machine_id = string
    }
  ))
}

variable "source" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      port               = number
      virtual_machine_id = string
    }
  ))
  default = []
}

variable "test_configuration" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      http_configuration = list(object(
        {
          method       = string
          path         = string
          port         = number
          prefer_https = bool
          request_header = set(object(
            {
              name  = string
              value = string
            }
          ))
          valid_status_code_ranges = set(string)
        }
      ))
      icmp_configuration = list(object(
        {
          trace_route_enabled = bool
        }
      ))
      name                 = string
      preferred_ip_version = string
      protocol             = string
      success_threshold = list(object(
        {
          checks_failed_percent = number
          round_trip_time_ms    = number
        }
      ))
      tcp_configuration = list(object(
        {
          port                = number
          trace_route_enabled = bool
        }
      ))
      test_frequency_in_seconds = number
    }
  ))
}

variable "test_group" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      destination_endpoints    = set(string)
      enabled                  = bool
      name                     = string
      source_endpoints         = set(string)
      test_configuration_names = set(string)
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
resource "azurerm_network_connection_monitor" "this" {
  auto_start                    = var.auto_start
  interval_in_seconds           = var.interval_in_seconds
  location                      = var.location
  name                          = var.name
  network_watcher_id            = var.network_watcher_id
  notes                         = var.notes
  output_workspace_resource_ids = var.output_workspace_resource_ids
  tags                          = var.tags

  dynamic "destination" {
    for_each = var.destination
    content {
      address            = destination.value["address"]
      port               = destination.value["port"]
      virtual_machine_id = destination.value["virtual_machine_id"]
    }
  }

  dynamic "endpoint" {
    for_each = var.endpoint
    content {
      address            = endpoint.value["address"]
      name               = endpoint.value["name"]
      virtual_machine_id = endpoint.value["virtual_machine_id"]

      dynamic "filter" {
        for_each = endpoint.value.filter
        content {
          type = filter.value["type"]

          dynamic "item" {
            for_each = filter.value.item
            content {
              address = item.value["address"]
              type    = item.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      port               = source.value["port"]
      virtual_machine_id = source.value["virtual_machine_id"]
    }
  }

  dynamic "test_configuration" {
    for_each = var.test_configuration
    content {
      name                      = test_configuration.value["name"]
      preferred_ip_version      = test_configuration.value["preferred_ip_version"]
      protocol                  = test_configuration.value["protocol"]
      test_frequency_in_seconds = test_configuration.value["test_frequency_in_seconds"]

      dynamic "http_configuration" {
        for_each = test_configuration.value.http_configuration
        content {
          method                   = http_configuration.value["method"]
          path                     = http_configuration.value["path"]
          port                     = http_configuration.value["port"]
          prefer_https             = http_configuration.value["prefer_https"]
          valid_status_code_ranges = http_configuration.value["valid_status_code_ranges"]

          dynamic "request_header" {
            for_each = http_configuration.value.request_header
            content {
              name  = request_header.value["name"]
              value = request_header.value["value"]
            }
          }

        }
      }

      dynamic "icmp_configuration" {
        for_each = test_configuration.value.icmp_configuration
        content {
          trace_route_enabled = icmp_configuration.value["trace_route_enabled"]
        }
      }

      dynamic "success_threshold" {
        for_each = test_configuration.value.success_threshold
        content {
          checks_failed_percent = success_threshold.value["checks_failed_percent"]
          round_trip_time_ms    = success_threshold.value["round_trip_time_ms"]
        }
      }

      dynamic "tcp_configuration" {
        for_each = test_configuration.value.tcp_configuration
        content {
          port                = tcp_configuration.value["port"]
          trace_route_enabled = tcp_configuration.value["trace_route_enabled"]
        }
      }

    }
  }

  dynamic "test_group" {
    for_each = var.test_group
    content {
      destination_endpoints    = test_group.value["destination_endpoints"]
      enabled                  = test_group.value["enabled"]
      name                     = test_group.value["name"]
      source_endpoints         = test_group.value["source_endpoints"]
      test_configuration_names = test_group.value["test_configuration_names"]
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
output "auto_start" {
  description = "returns a bool"
  value       = azurerm_network_connection_monitor.this.auto_start
}

output "id" {
  description = "returns a string"
  value       = azurerm_network_connection_monitor.this.id
}

output "interval_in_seconds" {
  description = "returns a number"
  value       = azurerm_network_connection_monitor.this.interval_in_seconds
}

output "output_workspace_resource_ids" {
  description = "returns a set of string"
  value       = azurerm_network_connection_monitor.this.output_workspace_resource_ids
}

output "this" {
  value = azurerm_network_connection_monitor.this
}
```

[top](#index)