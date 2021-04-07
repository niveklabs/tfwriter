# azurerm_site_recovery_replication_policy

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
module "azurerm_site_recovery_replication_policy" {
  source = "./modules/azurerm/r/azurerm_site_recovery_replication_policy"

  # application_consistent_snapshot_frequency_in_minutes - (required) is a type of number
  application_consistent_snapshot_frequency_in_minutes = null
  # name - (required) is a type of string
  name = null
  # recovery_point_retention_in_minutes - (required) is a type of number
  recovery_point_retention_in_minutes = null
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "application_consistent_snapshot_frequency_in_minutes" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "recovery_point_retention_in_minutes" {
  description = "(required)"
  type        = number
}

variable "recovery_vault_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
resource "azurerm_site_recovery_replication_policy" "this" {
  # application_consistent_snapshot_frequency_in_minutes - (required) is a type of number
  application_consistent_snapshot_frequency_in_minutes = var.application_consistent_snapshot_frequency_in_minutes
  # name - (required) is a type of string
  name = var.name
  # recovery_point_retention_in_minutes - (required) is a type of number
  recovery_point_retention_in_minutes = var.recovery_point_retention_in_minutes
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = var.recovery_vault_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
  value       = azurerm_site_recovery_replication_policy.this.id
}

output "this" {
  value = azurerm_site_recovery_replication_policy.this
}
```

[top](#index)