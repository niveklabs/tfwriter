# azurerm_search_service

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
module "azurerm_search_service" {
  source = "./modules/azurerm/r/azurerm_search_service"

  # allowed_ips - (optional) is a type of list of string
  allowed_ips = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # partition_count - (optional) is a type of number
  partition_count = null
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = null
  # replica_count - (optional) is a type of number
  replica_count = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (required) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "allowed_ips" {
  description = "(optional)"
  type        = list(string)
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

variable "partition_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "public_network_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "replica_count" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "azurerm_search_service" "this" {
  # allowed_ips - (optional) is a type of list of string
  allowed_ips = var.allowed_ips
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # partition_count - (optional) is a type of number
  partition_count = var.partition_count
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = var.public_network_access_enabled
  # replica_count - (optional) is a type of number
  replica_count = var.replica_count
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku - (required) is a type of string
  sku = var.sku
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "identity" {
    for_each = var.identity
    content {
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

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
  value       = azurerm_search_service.this.id
}

output "partition_count" {
  description = "returns a number"
  value       = azurerm_search_service.this.partition_count
}

output "primary_key" {
  description = "returns a string"
  value       = azurerm_search_service.this.primary_key
}

output "query_keys" {
  description = "returns a list of object"
  value       = azurerm_search_service.this.query_keys
}

output "replica_count" {
  description = "returns a number"
  value       = azurerm_search_service.this.replica_count
}

output "secondary_key" {
  description = "returns a string"
  value       = azurerm_search_service.this.secondary_key
}

output "this" {
  value = azurerm_search_service.this
}
```

[top](#index)