# azurerm_storage_table

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_storage_table" {
  source = "./modules/azurerm/r/azurerm_storage_table"

  # name - (required) is a type of string
  name = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null

  acl = [{
    access_policy = [{
      expiry      = null
      permissions = null
      start       = null
    }]
    id = null
  }]

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

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "acl" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_policy = list(object(
        {
          expiry      = string
          permissions = string
          start       = string
        }
      ))
      id = string
    }
  ))
  default = []
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
resource "azurerm_storage_table" "this" {
  name                 = var.name
  storage_account_name = var.storage_account_name

  dynamic "acl" {
    for_each = var.acl
    content {
      id = acl.value["id"]

      dynamic "access_policy" {
        for_each = acl.value.access_policy
        content {
          expiry      = access_policy.value["expiry"]
          permissions = access_policy.value["permissions"]
          start       = access_policy.value["start"]
        }
      }

    }
  }

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
  value       = azurerm_storage_table.this.id
}

output "this" {
  value = azurerm_storage_table.this
}
```

[top](#index)