# pagerduty_schedule

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_schedule" {
  source = "./modules/pagerduty/r/pagerduty_schedule"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # overflow - (optional) is a type of bool
  overflow = null
  # time_zone - (required) is a type of string
  time_zone = null

  layer = [{
    end  = null
    id   = null
    name = null
    restriction = [{
      duration_seconds  = null
      start_day_of_week = null
      start_time_of_day = null
      type              = null
    }]
    rotation_turn_length_seconds = null
    rotation_virtual_start       = null
    start                        = null
    users                        = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "overflow" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "time_zone" {
  description = "(required)"
  type        = string
}

variable "layer" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      end  = string
      id   = string
      name = string
      restriction = list(object(
        {
          duration_seconds  = number
          start_day_of_week = number
          start_time_of_day = string
          type              = string
        }
      ))
      rotation_turn_length_seconds = number
      rotation_virtual_start       = string
      start                        = string
      users                        = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_schedule" "this" {
  description = var.description
  name        = var.name
  overflow    = var.overflow
  time_zone   = var.time_zone

  dynamic "layer" {
    for_each = var.layer
    content {
      end                          = layer.value["end"]
      name                         = layer.value["name"]
      rotation_turn_length_seconds = layer.value["rotation_turn_length_seconds"]
      rotation_virtual_start       = layer.value["rotation_virtual_start"]
      start                        = layer.value["start"]
      users                        = layer.value["users"]

      dynamic "restriction" {
        for_each = layer.value.restriction
        content {
          duration_seconds  = restriction.value["duration_seconds"]
          start_day_of_week = restriction.value["start_day_of_week"]
          start_time_of_day = restriction.value["start_time_of_day"]
          type              = restriction.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_schedule.this.id
}

output "this" {
  value = pagerduty_schedule.this
}
```

[top](#index)