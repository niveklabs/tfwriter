# newrelic_events_to_metrics_rule

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
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_events_to_metrics_rule" {
  source = "./modules/newrelic/r/newrelic_events_to_metrics_rule"

  # account_id - (optional) is a type of number
  account_id = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # nrql - (required) is a type of string
  nrql = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - Account with the event and where the metrics will be put."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Provides additional information about the rule."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - True means this rule is enabled. False means the rule is currently not creating metrics."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of the rule. This must be unique within an account."
  type        = string
}

variable "nrql" {
  description = "(required) - Explains how to create metrics from events."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_events_to_metrics_rule" "this" {
  account_id  = var.account_id
  description = var.description
  enabled     = var.enabled
  name        = var.name
  nrql        = var.nrql
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_events_to_metrics_rule.this.account_id
}

output "id" {
  description = "returns a string"
  value       = newrelic_events_to_metrics_rule.this.id
}

output "rule_id" {
  description = "returns a string"
  value       = newrelic_events_to_metrics_rule.this.rule_id
}

output "this" {
  value = newrelic_events_to_metrics_rule.this
}
```

[top](#index)