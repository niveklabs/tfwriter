# opsgenie_schedule_rotation

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_schedule_rotation" {
  source = "./modules/opsgenie/r/opsgenie_schedule_rotation"

  # end_date - (optional) is a type of string
  end_date = null
  # length - (optional) is a type of number
  length = null
  # name - (optional) is a type of string
  name = null
  # schedule_id - (required) is a type of string
  schedule_id = null
  # start_date - (required) is a type of string
  start_date = null
  # type - (required) is a type of string
  type = null

  participant = [{
    id   = null
    type = null
  }]

  time_restriction = [{
    restriction = [{
      end_hour   = null
      end_min    = null
      start_hour = null
      start_min  = null
    }]
    restrictions = [{
      end_day    = null
      end_hour   = null
      end_min    = null
      start_day  = null
      start_hour = null
      start_min  = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "end_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_id" {
  description = "(required)"
  type        = string
}

variable "start_date" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "participant" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      id   = string
      type = string
    }
  ))
}

variable "time_restriction" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      restriction = list(object(
        {
          end_hour   = number
          end_min    = number
          start_hour = number
          start_min  = number
        }
      ))
      restrictions = list(object(
        {
          end_day    = string
          end_hour   = number
          end_min    = number
          start_day  = string
          start_hour = number
          start_min  = number
        }
      ))
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_schedule_rotation" "this" {
  end_date    = var.end_date
  length      = var.length
  name        = var.name
  schedule_id = var.schedule_id
  start_date  = var.start_date
  type        = var.type

  dynamic "participant" {
    for_each = var.participant
    content {
      id   = participant.value["id"]
      type = participant.value["type"]
    }
  }

  dynamic "time_restriction" {
    for_each = var.time_restriction
    content {
      type = time_restriction.value["type"]

      dynamic "restriction" {
        for_each = time_restriction.value.restriction
        content {
          end_hour   = restriction.value["end_hour"]
          end_min    = restriction.value["end_min"]
          start_hour = restriction.value["start_hour"]
          start_min  = restriction.value["start_min"]
        }
      }

      dynamic "restrictions" {
        for_each = time_restriction.value.restrictions
        content {
          end_day    = restrictions.value["end_day"]
          end_hour   = restrictions.value["end_hour"]
          end_min    = restrictions.value["end_min"]
          start_day  = restrictions.value["start_day"]
          start_hour = restrictions.value["start_hour"]
          start_min  = restrictions.value["start_min"]
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
  value       = opsgenie_schedule_rotation.this.id
}

output "this" {
  value = opsgenie_schedule_rotation.this
}
```

[top](#index)