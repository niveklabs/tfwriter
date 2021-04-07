# pagerduty_user_notification_rule

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
module "pagerduty_user_notification_rule" {
  source = "./modules/pagerduty/r/pagerduty_user_notification_rule"

  # contact_method - (required) is a type of map of string
  contact_method = {}
  # start_delay_in_minutes - (required) is a type of number
  start_delay_in_minutes = null
  # urgency - (required) is a type of string
  urgency = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "contact_method" {
  description = "(required)"
  type        = map(string)
}

variable "start_delay_in_minutes" {
  description = "(required)"
  type        = number
}

variable "urgency" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_user_notification_rule" "this" {
  # contact_method - (required) is a type of map of string
  contact_method = var.contact_method
  # start_delay_in_minutes - (required) is a type of number
  start_delay_in_minutes = var.start_delay_in_minutes
  # urgency - (required) is a type of string
  urgency = var.urgency
  # user_id - (required) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_user_notification_rule.this.id
}

output "this" {
  value = pagerduty_user_notification_rule.this
}
```

[top](#index)