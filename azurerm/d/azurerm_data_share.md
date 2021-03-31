# azurerm_data_share

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
module "azurerm_data_share" {
  source = "./modules/azurerm/d/azurerm_data_share"

  # account_id - (required) is a type of string
  account_id = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "name" {
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
data "azurerm_data_share" "this" {
  account_id = var.account_id
  name       = var.name

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
output "description" {
  description = "returns a string"
  value       = data.azurerm_data_share.this.description
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_share.this.id
}

output "kind" {
  description = "returns a string"
  value       = data.azurerm_data_share.this.kind
}

output "snapshot_schedule" {
  description = "returns a list of object"
  value       = data.azurerm_data_share.this.snapshot_schedule
}

output "terms" {
  description = "returns a string"
  value       = data.azurerm_data_share.this.terms
}

output "this" {
  value = azurerm_data_share.this
}
```

[top](#index)