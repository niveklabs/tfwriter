# azurerm_user_assigned_identity

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_user_assigned_identity" {
  source = "./modules/azurerm/d/azurerm_user_assigned_identity"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_user_assigned_identity" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = data.azurerm_user_assigned_identity.this.client_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_user_assigned_identity.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_user_assigned_identity.this.location
}

output "principal_id" {
  description = "returns a string"
  value       = data.azurerm_user_assigned_identity.this.principal_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_user_assigned_identity.this.tags
}

output "this" {
  value = azurerm_user_assigned_identity.this
}
```

[top](#index)