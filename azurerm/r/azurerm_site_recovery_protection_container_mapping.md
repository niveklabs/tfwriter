# azurerm_site_recovery_protection_container_mapping

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
module "azurerm_site_recovery_protection_container_mapping" {
  source = "./modules/azurerm/r/azurerm_site_recovery_protection_container_mapping"

  # name - (required) is a type of string
  name = null
  # recovery_fabric_name - (required) is a type of string
  recovery_fabric_name = null
  # recovery_replication_policy_id - (required) is a type of string
  recovery_replication_policy_id = null
  # recovery_source_protection_container_name - (required) is a type of string
  recovery_source_protection_container_name = null
  # recovery_target_protection_container_id - (required) is a type of string
  recovery_target_protection_container_id = null
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
variable "name" {
  description = "(required)"
  type        = string
}

variable "recovery_fabric_name" {
  description = "(required)"
  type        = string
}

variable "recovery_replication_policy_id" {
  description = "(required)"
  type        = string
}

variable "recovery_source_protection_container_name" {
  description = "(required)"
  type        = string
}

variable "recovery_target_protection_container_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_site_recovery_protection_container_mapping" "this" {
  # name - (required) is a type of string
  name = var.name
  # recovery_fabric_name - (required) is a type of string
  recovery_fabric_name = var.recovery_fabric_name
  # recovery_replication_policy_id - (required) is a type of string
  recovery_replication_policy_id = var.recovery_replication_policy_id
  # recovery_source_protection_container_name - (required) is a type of string
  recovery_source_protection_container_name = var.recovery_source_protection_container_name
  # recovery_target_protection_container_id - (required) is a type of string
  recovery_target_protection_container_id = var.recovery_target_protection_container_id
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
  value       = azurerm_site_recovery_protection_container_mapping.this.id
}

output "this" {
  value = azurerm_site_recovery_protection_container_mapping.this
}
```

[top](#index)