# azurerm_netapp_snapshot

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_netapp_snapshot" {
  source = "./modules/azurerm/d/azurerm_netapp_snapshot"

  # account_name - (required) is a type of string
  account_name = null
  # name - (required) is a type of string
  name = null
  # pool_name - (required) is a type of string
  pool_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # volume_name - (required) is a type of string
  volume_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pool_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "volume_name" {
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
data "azurerm_netapp_snapshot" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # name - (required) is a type of string
  name = var.name
  # pool_name - (required) is a type of string
  pool_name = var.pool_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # volume_name - (required) is a type of string
  volume_name = var.volume_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_netapp_snapshot.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_netapp_snapshot.this.location
}

output "this" {
  value = azurerm_netapp_snapshot.this
}
```

[top](#index)