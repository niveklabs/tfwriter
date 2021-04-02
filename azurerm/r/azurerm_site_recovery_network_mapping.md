# azurerm_site_recovery_network_mapping

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
module "azurerm_site_recovery_network_mapping" {
  source = "./modules/azurerm/r/azurerm_site_recovery_network_mapping"

  # name - (required) is a type of string
  name = null
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_network_id - (required) is a type of string
  source_network_id = null
  # source_recovery_fabric_name - (required) is a type of string
  source_recovery_fabric_name = null
  # target_network_id - (required) is a type of string
  target_network_id = null
  # target_recovery_fabric_name - (required) is a type of string
  target_recovery_fabric_name = null

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

variable "recovery_vault_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_network_id" {
  description = "(required)"
  type        = string
}

variable "source_recovery_fabric_name" {
  description = "(required)"
  type        = string
}

variable "target_network_id" {
  description = "(required)"
  type        = string
}

variable "target_recovery_fabric_name" {
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
resource "azurerm_site_recovery_network_mapping" "this" {
  name                        = var.name
  recovery_vault_name         = var.recovery_vault_name
  resource_group_name         = var.resource_group_name
  source_network_id           = var.source_network_id
  source_recovery_fabric_name = var.source_recovery_fabric_name
  target_network_id           = var.target_network_id
  target_recovery_fabric_name = var.target_recovery_fabric_name

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
  value       = azurerm_site_recovery_network_mapping.this.id
}

output "this" {
  value = azurerm_site_recovery_network_mapping.this
}
```

[top](#index)