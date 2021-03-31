# azurerm_data_lake_store_file

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
module "azurerm_data_lake_store_file" {
  source = "./modules/azurerm/r/azurerm_data_lake_store_file"

  # account_name - (required) is a type of string
  account_name = null
  # local_file_path - (required) is a type of string
  local_file_path = null
  # remote_file_path - (required) is a type of string
  remote_file_path = null

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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "local_file_path" {
  description = "(required)"
  type        = string
}

variable "remote_file_path" {
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
resource "azurerm_data_lake_store_file" "this" {
  account_name     = var.account_name
  local_file_path  = var.local_file_path
  remote_file_path = var.remote_file_path

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
  value       = azurerm_data_lake_store_file.this.id
}

output "this" {
  value = azurerm_data_lake_store_file.this
}
```

[top](#index)