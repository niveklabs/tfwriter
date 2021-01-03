# azurerm_iothub

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
module "azurerm_iothub" {
  source = "./modules/azurerm/r/azurerm_iothub"

  # endpoint - (optional) is a type of list of object
  endpoint = [{
    batch_frequency_in_seconds = null
    connection_string          = null
    container_name             = null
    encoding                   = null
    file_name_format           = null
    max_chunk_size_in_bytes    = null
    name                       = null
    resource_group_name        = null
    type                       = null
  }]
  # event_hub_partition_count - (optional) is a type of number
  event_hub_partition_count = null
  # event_hub_retention_in_days - (optional) is a type of number
  event_hub_retention_in_days = null
  # location - (required) is a type of string
  location = null
  # min_tls_version - (optional) is a type of string
  min_tls_version = null
  # name - (required) is a type of string
  name = null
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route - (optional) is a type of list of object
  route = [{
    condition      = null
    enabled        = null
    endpoint_names = []
    name           = null
    source         = null
  }]
  # tags - (optional) is a type of map of string
  tags = {}

  fallback_route = [{
    condition      = null
    enabled        = null
    endpoint_names = []
    source         = null
  }]

  file_upload = [{
    connection_string  = null
    container_name     = null
    default_ttl        = null
    lock_duration      = null
    max_delivery_count = null
    notifications      = null
    sas_ttl            = null
  }]

  ip_filter_rule = [{
    action  = null
    ip_mask = null
    name    = null
  }]

  sku = [{
    capacity = null
    name     = null
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
variable "endpoint" {
  description = "(optional)"
  type = list(object(
    {
      batch_frequency_in_seconds = number
      connection_string          = string
      container_name             = string
      encoding                   = string
      file_name_format           = string
      max_chunk_size_in_bytes    = number
      name                       = string
      resource_group_name        = string
      type                       = string
    }
  ))
  default = null
}

variable "event_hub_partition_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "event_hub_retention_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "min_tls_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_network_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "route" {
  description = "(optional)"
  type = list(object(
    {
      condition      = string
      enabled        = bool
      endpoint_names = list(string)
      name           = string
      source         = string
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "fallback_route" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      condition      = string
      enabled        = bool
      endpoint_names = list(string)
      source         = string
    }
  ))
  default = []
}

variable "file_upload" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_string  = string
      container_name     = string
      default_ttl        = string
      lock_duration      = string
      max_delivery_count = number
      notifications      = bool
      sas_ttl            = string
    }
  ))
  default = []
}

variable "ip_filter_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action  = string
      ip_mask = string
      name    = string
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      name     = string
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
resource "azurerm_iothub" "this" {
  endpoint                      = var.endpoint
  event_hub_partition_count     = var.event_hub_partition_count
  event_hub_retention_in_days   = var.event_hub_retention_in_days
  location                      = var.location
  min_tls_version               = var.min_tls_version
  name                          = var.name
  public_network_access_enabled = var.public_network_access_enabled
  resource_group_name           = var.resource_group_name
  route                         = var.route
  tags                          = var.tags

  dynamic "fallback_route" {
    for_each = var.fallback_route
    content {
      condition      = fallback_route.value["condition"]
      enabled        = fallback_route.value["enabled"]
      endpoint_names = fallback_route.value["endpoint_names"]
      source         = fallback_route.value["source"]
    }
  }

  dynamic "file_upload" {
    for_each = var.file_upload
    content {
      connection_string  = file_upload.value["connection_string"]
      container_name     = file_upload.value["container_name"]
      default_ttl        = file_upload.value["default_ttl"]
      lock_duration      = file_upload.value["lock_duration"]
      max_delivery_count = file_upload.value["max_delivery_count"]
      notifications      = file_upload.value["notifications"]
      sas_ttl            = file_upload.value["sas_ttl"]
    }
  }

  dynamic "ip_filter_rule" {
    for_each = var.ip_filter_rule
    content {
      action  = ip_filter_rule.value["action"]
      ip_mask = ip_filter_rule.value["ip_mask"]
      name    = ip_filter_rule.value["name"]
    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      capacity = sku.value["capacity"]
      name     = sku.value["name"]
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
output "endpoint" {
  description = "returns a list of object"
  value       = azurerm_iothub.this.endpoint
}

output "event_hub_events_endpoint" {
  description = "returns a string"
  value       = azurerm_iothub.this.event_hub_events_endpoint
}

output "event_hub_events_path" {
  description = "returns a string"
  value       = azurerm_iothub.this.event_hub_events_path
}

output "event_hub_operations_endpoint" {
  description = "returns a string"
  value       = azurerm_iothub.this.event_hub_operations_endpoint
}

output "event_hub_operations_path" {
  description = "returns a string"
  value       = azurerm_iothub.this.event_hub_operations_path
}

output "event_hub_partition_count" {
  description = "returns a number"
  value       = azurerm_iothub.this.event_hub_partition_count
}

output "event_hub_retention_in_days" {
  description = "returns a number"
  value       = azurerm_iothub.this.event_hub_retention_in_days
}

output "hostname" {
  description = "returns a string"
  value       = azurerm_iothub.this.hostname
}

output "id" {
  description = "returns a string"
  value       = azurerm_iothub.this.id
}

output "route" {
  description = "returns a list of object"
  value       = azurerm_iothub.this.route
}

output "shared_access_policy" {
  description = "returns a list of object"
  value       = azurerm_iothub.this.shared_access_policy
}

output "type" {
  description = "returns a string"
  value       = azurerm_iothub.this.type
}

output "this" {
  value = azurerm_iothub.this
}
```

[top](#index)