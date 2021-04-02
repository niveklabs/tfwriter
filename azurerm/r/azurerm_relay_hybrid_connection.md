# azurerm_relay_hybrid_connection

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
module "azurerm_relay_hybrid_connection" {
  source = "./modules/azurerm/r/azurerm_relay_hybrid_connection"

  # name - (required) is a type of string
  name = null
  # relay_namespace_name - (required) is a type of string
  relay_namespace_name = null
  # requires_client_authorization - (optional) is a type of bool
  requires_client_authorization = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # user_metadata - (optional) is a type of string
  user_metadata = null

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

variable "relay_namespace_name" {
  description = "(required)"
  type        = string
}

variable "requires_client_authorization" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "user_metadata" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_relay_hybrid_connection" "this" {
  name                          = var.name
  relay_namespace_name          = var.relay_namespace_name
  requires_client_authorization = var.requires_client_authorization
  resource_group_name           = var.resource_group_name
  user_metadata                 = var.user_metadata

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
  value       = azurerm_relay_hybrid_connection.this.id
}

output "this" {
  value = azurerm_relay_hybrid_connection.this
}
```

[top](#index)