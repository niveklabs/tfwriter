# pagerduty_escalation_policy

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
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_escalation_policy" {
  source = "./modules/pagerduty/r/pagerduty_escalation_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # num_loops - (optional) is a type of number
  num_loops = null
  # teams - (optional) is a type of list of string
  teams = []

  rule = [{
    escalation_delay_in_minutes = null
    id                          = null
    target = [{
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

variable "num_loops" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "teams" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
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
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_escalation_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # num_loops - (optional) is a type of number
  num_loops = var.num_loops
  # teams - (optional) is a type of list of string
  teams = var.teams

  dynamic "rule" {
    for_each = var.rule
    content {
      # escalation_delay_in_minutes - (required) is a type of number
      escalation_delay_in_minutes = rule.value["escalation_delay_in_minutes"]

      dynamic "target" {
        for_each = rule.value.target
        content {
          # id - (required) is a type of string
          id = target.value["id"]
          # type - (optional) is a type of string
          type = target.value["type"]
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
  value       = pagerduty_escalation_policy.this.id
}

output "this" {
  value = pagerduty_escalation_policy.this
}
```

[top](#index)