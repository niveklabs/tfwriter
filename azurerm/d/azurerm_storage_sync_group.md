# azurerm_storage_sync_group

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
module "azurerm_storage_sync_group" {
  source = "./modules/azurerm/d/azurerm_storage_sync_group"

  # name - (required) is a type of string
  name = null
  # storage_sync_id - (required) is a type of string
  storage_sync_id = null

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

variable "storage_sync_id" {
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
data "azurerm_storage_sync_group" "this" {
  # name - (required) is a type of string
  name = var.name
  # storage_sync_id - (required) is a type of string
  storage_sync_id = var.storage_sync_id

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
  value       = data.azurerm_storage_sync_group.this.id
}

output "this" {
  value = azurerm_storage_sync_group.this
}
```

[top](#index)