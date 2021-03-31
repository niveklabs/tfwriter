# azurerm_eventhub_namespace_disaster_recovery_config

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
module "azurerm_eventhub_namespace_disaster_recovery_config" {
  source = "./modules/azurerm/r/azurerm_eventhub_namespace_disaster_recovery_config"

  # alternate_name - (optional) is a type of string
  alternate_name = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # partner_namespace_id - (required) is a type of string
  partner_namespace_id = null
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
variable "alternate_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "partner_namespace_id" {
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
resource "azurerm_eventhub_namespace_disaster_recovery_config" "this" {
  alternate_name       = var.alternate_name
  name                 = var.name
  namespace_name       = var.namespace_name
  partner_namespace_id = var.partner_namespace_id
  resource_group_name  = var.resource_group_name

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
  value       = azurerm_eventhub_namespace_disaster_recovery_config.this.id
}

output "this" {
  value = azurerm_eventhub_namespace_disaster_recovery_config.this
}
```

[top](#index)