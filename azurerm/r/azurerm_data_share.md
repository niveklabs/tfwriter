# azurerm_data_share

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
module "azurerm_data_share" {
  source = "./modules/azurerm/r/azurerm_data_share"

  # account_id - (required) is a type of string
  account_id = null
  # description - (optional) is a type of string
  description = null
  # kind - (required) is a type of string
  kind = null
  # name - (required) is a type of string
  name = null
  # terms - (optional) is a type of string
  terms = null

  snapshot_schedule = [{
    name       = null
    recurrence = null
    start_time = null
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
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kind" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "terms" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_schedule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name       = string
      recurrence = string
      start_time = string
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
resource "azurerm_data_share" "this" {
  account_id  = var.account_id
  description = var.description
  kind        = var.kind
  name        = var.name
  terms       = var.terms

  dynamic "snapshot_schedule" {
    for_each = var.snapshot_schedule
    content {
      name       = snapshot_schedule.value["name"]
      recurrence = snapshot_schedule.value["recurrence"]
      start_time = snapshot_schedule.value["start_time"]
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
  value       = azurerm_data_share.this.id
}

output "this" {
  value = azurerm_data_share.this
}
```

[top](#index)