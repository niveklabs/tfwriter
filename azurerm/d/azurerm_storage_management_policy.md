# azurerm_storage_management_policy

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
module "azurerm_storage_management_policy" {
  source = "./modules/azurerm/d/azurerm_storage_management_policy"

  # storage_account_id - (required) is a type of string
  storage_account_id = null

  timeouts = [{
    read = null
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
data "azurerm_storage_management_policy" "this" {
  storage_account_id = var.storage_account_id

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_storage_management_policy.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = data.azurerm_storage_management_policy.this.rule
}

output "this" {
  value = azurerm_storage_management_policy.this
}
```

[top](#index)