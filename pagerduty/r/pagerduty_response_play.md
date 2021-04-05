# pagerduty_response_play

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
module "pagerduty_response_play" {
  source = "./modules/pagerduty/r/pagerduty_response_play"

  # conference_number - (optional) is a type of string
  conference_number = null
  # conference_url - (optional) is a type of string
  conference_url = null
  # description - (optional) is a type of string
  description = null
  # from - (required) is a type of string
  from = null
  # name - (required) is a type of string
  name = null
  # responders_message - (optional) is a type of string
  responders_message = null
  # runnability - (optional) is a type of string
  runnability = null
  # subscribers_message - (optional) is a type of string
  subscribers_message = null
  # team - (optional) is a type of string
  team = null
  # type - (optional) is a type of string
  type = null

  responder = [{
    description = null
    escalation_rule = [{
      escalation_delay_in_minutes = null
      id                          = null
      target = [{
        id   = null
        type = null
      }]
    }]
    id                            = null
    name                          = null
    num_loops                     = null
    on_call_handoff_notifications = null
    service = [{
      id   = null
      type = null
    }]
    team = [{
      id   = null
      type = null
    }]
    type = null
  }]

  subscriber = [{
    id   = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "conference_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conference_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "from" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "responders_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "runnability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscribers_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "team" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "responder" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      description = string
      escalation_rule = list(object(
        {
          escalation_delay_in_minutes = number
          id                          = string
          target = list(object(
            {
              id   = string
              type = string
            }
          ))
        }
      ))
      id                            = string
      name                          = string
      num_loops                     = number
      on_call_handoff_notifications = string
      service = list(object(
        {
          id   = string
          type = string
        }
      ))
      team = list(object(
        {
          id   = string
          type = string
        }
      ))
      type = string
    }
  ))
}

variable "subscriber" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_response_play" "this" {
  conference_number   = var.conference_number
  conference_url      = var.conference_url
  description         = var.description
  from                = var.from
  name                = var.name
  responders_message  = var.responders_message
  runnability         = var.runnability
  subscribers_message = var.subscribers_message
  team                = var.team
  type                = var.type

  dynamic "responder" {
    for_each = var.responder
    content {
      description = responder.value["description"]
      id          = responder.value["id"]
      name        = responder.value["name"]
      type        = responder.value["type"]
    }
  }

  dynamic "subscriber" {
    for_each = var.subscriber
    content {
      id   = subscriber.value["id"]
      type = subscriber.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_response_play.this.id
}

output "this" {
  value = pagerduty_response_play.this
}
```

[top](#index)