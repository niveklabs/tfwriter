# opsgenie_escalation

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "opsgenie_escalation" {
  source = "./modules/opsgenie/d/opsgenie_escalation"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # owner_team_id - (optional) is a type of string
  owner_team_id = null

  repeat = [{
    close_alert_after_all  = null
    count                  = null
    reset_recipient_states = null
    wait_interval          = null
  }]

  rules = [{
    condition   = null
    delay       = null
    notify_type = null
    recipient = [{
      id   = null
      type = null
    }]
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
  description = "(required)"
  type        = string
}

variable "owner_team_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repeat" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      close_alert_after_all  = bool
      count                  = number
      reset_recipient_states = bool
      wait_interval          = number
    }
  ))
  default = []
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      condition   = string
      delay       = number
      notify_type = string
      recipient = list(object(
        {
          id   = string
          type = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "opsgenie_escalation" "this" {
  description   = var.description
  name          = var.name
  owner_team_id = var.owner_team_id

  dynamic "repeat" {
    for_each = var.repeat
    content {
      close_alert_after_all  = repeat.value["close_alert_after_all"]
      count                  = repeat.value["count"]
      reset_recipient_states = repeat.value["reset_recipient_states"]
      wait_interval          = repeat.value["wait_interval"]
    }
  }

  dynamic "rules" {
    for_each = var.rules
    content {
      condition   = rules.value["condition"]
      delay       = rules.value["delay"]
      notify_type = rules.value["notify_type"]

      dynamic "recipient" {
        for_each = rules.value.recipient
        content {
          id   = recipient.value["id"]
          type = recipient.value["type"]
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
  value       = data.opsgenie_escalation.this.id
}

output "this" {
  value = opsgenie_escalation.this
}
```

[top](#index)