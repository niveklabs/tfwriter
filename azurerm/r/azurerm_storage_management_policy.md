# azurerm_storage_management_policy

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
module "azurerm_storage_management_policy" {
  source = "./modules/azurerm/r/azurerm_storage_management_policy"

  # storage_account_id - (required) is a type of string
  storage_account_id = null

  rule = [{
    actions = [{
      base_blob = [{
        delete_after_days_since_modification_greater_than          = null
        tier_to_archive_after_days_since_modification_greater_than = null
        tier_to_cool_after_days_since_modification_greater_than    = null
      }]
      snapshot = [{
        delete_after_days_since_creation_greater_than = null
      }]
    }]
    enabled = null
    filters = [{
      blob_types   = []
      prefix_match = []
    }]
    name = null
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
variable "storage_account_id" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      actions = list(object(
        {
          base_blob = list(object(
            {
              delete_after_days_since_modification_greater_than          = number
              tier_to_archive_after_days_since_modification_greater_than = number
              tier_to_cool_after_days_since_modification_greater_than    = number
            }
          ))
          snapshot = list(object(
            {
              delete_after_days_since_creation_greater_than = number
            }
          ))
        }
      ))
      enabled = bool
      filters = list(object(
        {
          blob_types   = set(string)
          prefix_match = set(string)
        }
      ))
      name = string
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
resource "azurerm_storage_management_policy" "this" {
  storage_account_id = var.storage_account_id

  dynamic "rule" {
    for_each = var.rule
    content {
      enabled = rule.value["enabled"]
      name    = rule.value["name"]

      dynamic "actions" {
        for_each = rule.value.actions
        content {

          dynamic "base_blob" {
            for_each = actions.value.base_blob
            content {
              delete_after_days_since_modification_greater_than          = base_blob.value["delete_after_days_since_modification_greater_than"]
              tier_to_archive_after_days_since_modification_greater_than = base_blob.value["tier_to_archive_after_days_since_modification_greater_than"]
              tier_to_cool_after_days_since_modification_greater_than    = base_blob.value["tier_to_cool_after_days_since_modification_greater_than"]
            }
          }

          dynamic "snapshot" {
            for_each = actions.value.snapshot
            content {
              delete_after_days_since_creation_greater_than = snapshot.value["delete_after_days_since_creation_greater_than"]
            }
          }

        }
      }

      dynamic "filters" {
        for_each = rule.value.filters
        content {
          blob_types   = filters.value["blob_types"]
          prefix_match = filters.value["prefix_match"]
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
  value       = azurerm_storage_management_policy.this.id
}

output "this" {
  value = azurerm_storage_management_policy.this
}
```

[top](#index)