# newrelic_alert_muting_rule

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_alert_muting_rule" {
  source = "./modules/newrelic/r/newrelic_alert_muting_rule"

  # account_id - (optional) is a type of number
  account_id = null
  # description - (optional) is a type of string
  description = null
  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null

  condition = [{
    conditions = [{
      attribute = null
      operator  = null
      values    = []
    }]
    operator = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The account id of the MutingRule.."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The description of the MutingRule."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required) - Whether the MutingRule is enabled."
  type        = bool
}

variable "name" {
  description = "(required) - The name of the MutingRule."
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      conditions = list(object(
        {
          attribute = string
          operator  = string
          values    = list(string)
        }
      ))
      operator = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_alert_muting_rule" "this" {
  account_id  = var.account_id
  description = var.description
  enabled     = var.enabled
  name        = var.name

  dynamic "condition" {
    for_each = var.condition
    content {
      operator = condition.value["operator"]

      dynamic "conditions" {
        for_each = condition.value.conditions
        content {
          attribute = conditions.value["attribute"]
          operator  = conditions.value["operator"]
          values    = conditions.value["values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_alert_muting_rule.this.account_id
}

output "id" {
  description = "returns a string"
  value       = newrelic_alert_muting_rule.this.id
}

output "this" {
  value = newrelic_alert_muting_rule.this
}
```

[top](#index)