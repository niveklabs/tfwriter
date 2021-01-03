# opsgenie_alert_policy

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
    opsgenie = ">= 0.5.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_alert_policy" {
  source = null

  # actions - (optional) is a type of set of string
  actions = []
  # alert_description - (optional) is a type of string
  alert_description = null
  # alias - (optional) is a type of string
  alias = null
  # continue_policy - (optional) is a type of bool
  continue_policy = null
  # enabled - (optional) is a type of bool
  enabled = null
  # entity - (optional) is a type of string
  entity = null
  # ignore_original_actions - (optional) is a type of bool
  ignore_original_actions = null
  # ignore_original_details - (optional) is a type of bool
  ignore_original_details = null
  # ignore_original_responders - (optional) is a type of bool
  ignore_original_responders = null
  # ignore_original_tags - (optional) is a type of bool
  ignore_original_tags = null
  # message - (required) is a type of string
  message = null
  # name - (required) is a type of string
  name = null
  # policy_description - (optional) is a type of string
  policy_description = null
  # priority - (optional) is a type of string
  priority = null
  # source - (optional) is a type of string
  # tags - (optional) is a type of set of string
  tags = []
  # team_id - (optional) is a type of string
  team_id = null

  filter = [{
    conditions = [{
      expected_value = null
      field          = null
      key            = null
      not            = null
      operation      = null
      order          = null
    }]
    type = null
  }]

  responders = [{
    id       = null
    name     = null
    type     = null
    username = null
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
variable "actions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "alert_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "continue_policy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "entity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_original_actions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ignore_original_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ignore_original_responders" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ignore_original_tags" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "message" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "team_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      conditions = list(object(
        {
          expected_value = string
          field          = string
          key            = string
          not            = bool
          operation      = string
          order          = number
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "responders" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id       = string
      name     = string
      type     = string
      username = string
    }
  ))
  default = []
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
resource "opsgenie_alert_policy" "this" {
  actions                    = var.actions
  alert_description          = var.alert_description
  alias                      = var.alias
  continue_policy            = var.continue_policy
  enabled                    = var.enabled
  entity                     = var.entity
  ignore_original_actions    = var.ignore_original_actions
  ignore_original_details    = var.ignore_original_details
  ignore_original_responders = var.ignore_original_responders
  ignore_original_tags       = var.ignore_original_tags
  message                    = var.message
  name                       = var.name
  policy_description         = var.policy_description
  priority                   = var.priority
  source                     = var.source
  tags                       = var.tags
  team_id                    = var.team_id

  dynamic "filter" {
    for_each = var.filter
    content {
      type = filter.value["type"]

      dynamic "conditions" {
        for_each = filter.value.conditions
        content {
          expected_value = conditions.value["expected_value"]
          field          = conditions.value["field"]
          key            = conditions.value["key"]
          not            = conditions.value["not"]
          operation      = conditions.value["operation"]
          order          = conditions.value["order"]
        }
      }

    }
  }

  dynamic "responders" {
    for_each = var.responders
    content {
      id       = responders.value["id"]
      name     = responders.value["name"]
      type     = responders.value["type"]
      username = responders.value["username"]
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
  value       = opsgenie_alert_policy.this.id
}

output "this" {
  value = opsgenie_alert_policy.this
}
```

[top](#index)