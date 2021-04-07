# circonus_rule_set

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.12.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_rule_set" {
  source = "./modules/circonus/r/circonus_rule_set"

  # check - (required) is a type of string
  check = null
  # link - (optional) is a type of string
  link = null
  # metric_filter - (optional) is a type of string
  metric_filter = null
  # metric_name - (optional) is a type of string
  metric_name = null
  # metric_pattern - (optional) is a type of string
  metric_pattern = null
  # metric_type - (optional) is a type of string
  metric_type = null
  # name - (optional) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # parent - (optional) is a type of string
  parent = null
  # tags - (optional) is a type of set of string
  tags = []
  # user_json - (optional) is a type of string
  user_json = null

  if = [{
    then = [{
      after    = null
      notify   = []
      severity = null
    }]
    value = [{
      absent      = null
      changed     = null
      contains    = null
      eq_value    = null
      match       = null
      max_value   = null
      min_value   = null
      neq_value   = null
      not_contain = null
      not_match   = null
      over = [{
        atleast = null
        last    = null
        using   = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "check" {
  description = "(required) - The CID of the check that contains the metric for this rule set"
  type        = string
}

variable "link" {
  description = "(optional) - URL to show users when this rule set is active (e.g. wiki)"
  type        = string
  default     = null
}

variable "metric_filter" {
  description = "(optional) - The tag filter a pattern match ruleset will user"
  type        = string
  default     = null
}

variable "metric_name" {
  description = "(optional) - The name of the metric stream within a check to register the rule set with"
  type        = string
  default     = null
}

variable "metric_pattern" {
  description = "(optional) - The pattern match (regex) of the metric stream within a check to register the rule set with"
  type        = string
  default     = null
}

variable "metric_type" {
  description = "(optional) - The type of data flowing through the specified metric stream"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of this ruleset, if ommitted will default to the metric_name (or pattern) and filter"
  type        = string
  default     = null
}

variable "notes" {
  description = "(optional) - Notes describing this rule set"
  type        = string
  default     = null
}

variable "parent" {
  description = "(optional) - Parent CID that must be healthy for this rule set to be active"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags associated with this rule set"
  type        = set(string)
  default     = null
}

variable "user_json" {
  description = "(optional) - Opaque data that can be supplied with the result and appears in webhooks when alerts go off"
  type        = string
  default     = null
}

variable "if" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      then = list(object(
        {
          after    = string
          notify   = set(string)
          severity = number
        }
      ))
      value = list(object(
        {
          absent      = string
          changed     = string
          contains    = string
          eq_value    = string
          match       = string
          max_value   = string
          min_value   = string
          neq_value   = string
          not_contain = string
          not_match   = string
          over = list(object(
            {
              atleast = string
              last    = string
              using   = string
            }
          ))
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "circonus_rule_set" "this" {
  # check - (required) is a type of string
  check = var.check
  # link - (optional) is a type of string
  link = var.link
  # metric_filter - (optional) is a type of string
  metric_filter = var.metric_filter
  # metric_name - (optional) is a type of string
  metric_name = var.metric_name
  # metric_pattern - (optional) is a type of string
  metric_pattern = var.metric_pattern
  # metric_type - (optional) is a type of string
  metric_type = var.metric_type
  # name - (optional) is a type of string
  name = var.name
  # notes - (optional) is a type of string
  notes = var.notes
  # parent - (optional) is a type of string
  parent = var.parent
  # tags - (optional) is a type of set of string
  tags = var.tags
  # user_json - (optional) is a type of string
  user_json = var.user_json

  dynamic "if" {
    for_each = var.if
    content {

      dynamic "then" {
        for_each = if.value.then
        content {
          # after - (optional) is a type of string
          after = then.value["after"]
          # notify - (optional) is a type of set of string
          notify = then.value["notify"]
          # severity - (optional) is a type of number
          severity = then.value["severity"]
        }
      }

      dynamic "value" {
        for_each = if.value.value
        content {
          # absent - (optional) is a type of string
          absent = value.value["absent"]
          # changed - (optional) is a type of string
          changed = value.value["changed"]
          # contains - (optional) is a type of string
          contains = value.value["contains"]
          # eq_value - (optional) is a type of string
          eq_value = value.value["eq_value"]
          # match - (optional) is a type of string
          match = value.value["match"]
          # max_value - (optional) is a type of string
          max_value = value.value["max_value"]
          # min_value - (optional) is a type of string
          min_value = value.value["min_value"]
          # neq_value - (optional) is a type of string
          neq_value = value.value["neq_value"]
          # not_contain - (optional) is a type of string
          not_contain = value.value["not_contain"]
          # not_match - (optional) is a type of string
          not_match = value.value["not_match"]

          dynamic "over" {
            for_each = value.value.over
            content {
              # atleast - (optional) is a type of string
              atleast = over.value["atleast"]
              # last - (optional) is a type of string
              last = over.value["last"]
              # using - (optional) is a type of string
              using = over.value["using"]
            }
          }

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
  value       = circonus_rule_set.this.id
}

output "link" {
  description = "returns a string"
  value       = circonus_rule_set.this.link
}

output "notes" {
  description = "returns a string"
  value       = circonus_rule_set.this.notes
}

output "parent" {
  description = "returns a string"
  value       = circonus_rule_set.this.parent
}

output "rule_set_id" {
  description = "returns a string"
  value       = circonus_rule_set.this.rule_set_id
}

output "this" {
  value = circonus_rule_set.this
}
```

[top](#index)