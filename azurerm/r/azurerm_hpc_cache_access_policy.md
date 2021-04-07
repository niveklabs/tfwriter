# azurerm_hpc_cache_access_policy

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
module "azurerm_hpc_cache_access_policy" {
  source = "./modules/azurerm/r/azurerm_hpc_cache_access_policy"

  # hpc_cache_id - (required) is a type of string
  hpc_cache_id = null
  # name - (required) is a type of string
  name = null

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
variable "hpc_cache_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "access_rule" {
  description = "nested block: NestingSet, min items: 1, max items: 3"
  type = set(object(
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
resource "azurerm_hpc_cache_access_policy" "this" {
  # hpc_cache_id - (required) is a type of string
  hpc_cache_id = var.hpc_cache_id
  # name - (required) is a type of string
  name = var.name

  dynamic "access_rule" {
    for_each = var.access_rule
    content {
      # access - (required) is a type of string
      access = access_rule.value["access"]
      # anonymous_gid - (optional) is a type of number
      anonymous_gid = access_rule.value["anonymous_gid"]
      # anonymous_uid - (optional) is a type of number
      anonymous_uid = access_rule.value["anonymous_uid"]
      # filter - (optional) is a type of string
      filter = access_rule.value["filter"]
      # root_squash_enabled - (optional) is a type of bool
      root_squash_enabled = access_rule.value["root_squash_enabled"]
      # scope - (required) is a type of string
      scope = access_rule.value["scope"]
      # submount_access_enabled - (optional) is a type of bool
      submount_access_enabled = access_rule.value["submount_access_enabled"]
      # suid_enabled - (optional) is a type of bool
      suid_enabled = access_rule.value["suid_enabled"]
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
  value       = azurerm_hpc_cache_access_policy.this.id
}

output "this" {
  value = azurerm_hpc_cache_access_policy.this
}
```

[top](#index)