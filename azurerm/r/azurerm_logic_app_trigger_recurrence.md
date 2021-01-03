# azurerm_logic_app_trigger_recurrence

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
module "azurerm_logic_app_trigger_recurrence" {
  source = "./modules/azurerm/r/azurerm_logic_app_trigger_recurrence"

  # frequency - (required) is a type of string
  frequency = null
  # interval - (required) is a type of number
  interval = null
  # logic_app_id - (required) is a type of string
  logic_app_id = null
  # name - (required) is a type of string
  name = null
  # start_time - (optional) is a type of string
  start_time = null
  # time_zone - (optional) is a type of string
  time_zone = null

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
variable "frequency" {
  description = "(required)"
  type        = string
}

variable "interval" {
  description = "(required)"
  type        = number
}

variable "logic_app_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_zone" {
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
resource "azurerm_logic_app_trigger_recurrence" "this" {
  frequency    = var.frequency
  interval     = var.interval
  logic_app_id = var.logic_app_id
  name         = var.name
  start_time   = var.start_time
  time_zone    = var.time_zone

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
  value       = azurerm_logic_app_trigger_recurrence.this.id
}

output "time_zone" {
  description = "returns a string"
  value       = azurerm_logic_app_trigger_recurrence.this.time_zone
}

output "this" {
  value = azurerm_logic_app_trigger_recurrence.this
}
```

[top](#index)