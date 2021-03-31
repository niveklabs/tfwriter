# azurerm_eventhub_namespace

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
module "azurerm_eventhub_namespace" {
  source = "./modules/azurerm/r/azurerm_eventhub_namespace"

  # auto_inflate_enabled - (optional) is a type of bool
  auto_inflate_enabled = null
  # capacity - (optional) is a type of number
  capacity = null
  # dedicated_cluster_id - (optional) is a type of string
  dedicated_cluster_id = null
  # location - (required) is a type of string
  location = null
  # maximum_throughput_units - (optional) is a type of number
  maximum_throughput_units = null
  # name - (required) is a type of string
  name = null
  # network_rulesets - (optional) is a type of list of object
  network_rulesets = [{
    default_action = null
    ip_rule = [{
      action  = null
      ip_mask = null
    }]
    trusted_service_access_enabled = null
    virtual_network_rule = [{
      ignore_missing_virtual_network_service_endpoint = null
      subnet_id                                       = null
    }]
  }]
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (required) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_redundant - (optional) is a type of bool
  zone_redundant = null

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
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
variable "auto_inflate_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dedicated_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "maximum_throughput_units" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_rulesets" {
  description = "(optional)"
  type = list(object(
    {
      default_action = string
      ip_rule = list(object(
        {
          action  = string
          ip_mask = string
        }
      ))
      trusted_service_access_enabled = bool
      virtual_network_rule = list(object(
        {
          ignore_missing_virtual_network_service_endpoint = bool
          subnet_id                                       = string
        }
      ))
    }
  ))
  default = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_redundant" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
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
resource "azurerm_eventhub_namespace" "this" {
  auto_inflate_enabled     = var.auto_inflate_enabled
  capacity                 = var.capacity
  dedicated_cluster_id     = var.dedicated_cluster_id
  location                 = var.location
  maximum_throughput_units = var.maximum_throughput_units
  name                     = var.name
  network_rulesets         = var.network_rulesets
  resource_group_name      = var.resource_group_name
  sku                      = var.sku
  tags                     = var.tags
  zone_redundant           = var.zone_redundant

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
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
output "default_primary_connection_string" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.default_primary_connection_string
  sensitive   = true
}

output "default_primary_connection_string_alias" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.default_primary_connection_string_alias
  sensitive   = true
}

output "default_primary_key" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.default_primary_key
  sensitive   = true
}

output "default_secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.default_secondary_connection_string
  sensitive   = true
}

output "default_secondary_connection_string_alias" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.default_secondary_connection_string_alias
  sensitive   = true
}

output "default_secondary_key" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.default_secondary_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = azurerm_eventhub_namespace.this.id
}

output "maximum_throughput_units" {
  description = "returns a number"
  value       = azurerm_eventhub_namespace.this.maximum_throughput_units
}

output "network_rulesets" {
  description = "returns a list of object"
  value       = azurerm_eventhub_namespace.this.network_rulesets
}

output "this" {
  value = azurerm_eventhub_namespace.this
}
```

[top](#index)