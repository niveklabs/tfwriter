# pagerduty_event_rule

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
module "pagerduty_event_rule" {
  source = "./modules/pagerduty/r/pagerduty_event_rule"

  # action_json - (required) is a type of string
  action_json = null
  # advanced_condition_json - (optional) is a type of string
  advanced_condition_json = null
  # condition_json - (required) is a type of string
  condition_json = null
}
```

[top](#index)

### Variables

```terraform
variable "action_json" {
  description = "(required)"
  type        = string
}

variable "advanced_condition_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "condition_json" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_event_rule" "this" {
  action_json             = var.action_json
  advanced_condition_json = var.advanced_condition_json
  condition_json          = var.condition_json
}
```

[top](#index)

### Outputs

```terraform
output "catch_all" {
  description = "returns a bool"
  value       = pagerduty_event_rule.this.catch_all
}

output "id" {
  description = "returns a string"
  value       = pagerduty_event_rule.this.id
}

output "this" {
  value = pagerduty_event_rule.this
}
```

[top](#index)