# azurerm_hpc_cache

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
module "azurerm_hpc_cache" {
  source = "./modules/azurerm/r/azurerm_hpc_cache"

  # cache_size_in_gb - (required) is a type of number
  cache_size_in_gb = null
  # location - (required) is a type of string
  location = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # root_squash_enabled - (optional) is a type of bool
  root_squash_enabled = null
  # sku_name - (required) is a type of string
  sku_name = null
  # subnet_id - (required) is a type of string
  subnet_id = null

  default_access_policy = [{
    access_rule = [{
      access                  = null
      anonymous_gid           = null
      anonymous_uid           = null
      filter                  = null
      root_squash_enabled     = null
      scope                   = null
      submount_access_enabled = null
      suid_enabled            = null
    }]
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
variable "cache_size_in_gb" {
  description = "(required)"
  type        = number
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "root_squash_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "default_access_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_rule = set(object(
        {
          access                  = string
          anonymous_gid           = number
          anonymous_uid           = number
          filter                  = string
          root_squash_enabled     = bool
          scope                   = string
          submount_access_enabled = bool
          suid_enabled            = bool
        }
      ))
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
resource "azurerm_hpc_cache" "this" {
  cache_size_in_gb    = var.cache_size_in_gb
  location            = var.location
  mtu                 = var.mtu
  name                = var.name
  resource_group_name = var.resource_group_name
  root_squash_enabled = var.root_squash_enabled
  sku_name            = var.sku_name
  subnet_id           = var.subnet_id

  dynamic "default_access_policy" {
    for_each = var.default_access_policy
    content {

      dynamic "access_rule" {
        for_each = default_access_policy.value.access_rule
        content {
          access                  = access_rule.value["access"]
          anonymous_gid           = access_rule.value["anonymous_gid"]
          anonymous_uid           = access_rule.value["anonymous_uid"]
          filter                  = access_rule.value["filter"]
          root_squash_enabled     = access_rule.value["root_squash_enabled"]
          scope                   = access_rule.value["scope"]
          submount_access_enabled = access_rule.value["submount_access_enabled"]
          suid_enabled            = access_rule.value["suid_enabled"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_hpc_cache.this.id
}

output "mount_addresses" {
  description = "returns a list of string"
  value       = azurerm_hpc_cache.this.mount_addresses
}

output "root_squash_enabled" {
  description = "returns a bool"
  value       = azurerm_hpc_cache.this.root_squash_enabled
}

output "this" {
  value = azurerm_hpc_cache.this
}
```

[top](#index)