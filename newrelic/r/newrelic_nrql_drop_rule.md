# newrelic_nrql_drop_rule

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
module "newrelic_nrql_drop_rule" {
  source = "./modules/newrelic/r/newrelic_nrql_drop_rule"

  # account_id - (optional) is a type of number
  account_id = null
  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # nrql - (required) is a type of string
  nrql = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - Account with the NRQL drop rule will be put."
  type        = number
  default     = null
}

variable "action" {
  description = "(required) - The drop rule action (drop_data or drop_attributes)."
  type        = string
}

variable "description" {
  description = "(optional) - Provides additional information about the rule."
  type        = string
  default     = null
}

variable "nrql" {
  description = "(required) - Explains which data to apply the drop rule to."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_nrql_drop_rule" "this" {
  # account_id - (optional) is a type of number
  account_id = var.account_id
  # action - (required) is a type of string
  action = var.action
  # description - (optional) is a type of string
  description = var.description
  # nrql - (required) is a type of string
  nrql = var.nrql
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_nrql_drop_rule.this.account_id
}

output "id" {
  description = "returns a string"
  value       = newrelic_nrql_drop_rule.this.id
}

output "rule_id" {
  description = "returns a string"
  value       = newrelic_nrql_drop_rule.this.rule_id
}

output "this" {
  value = newrelic_nrql_drop_rule.this
}
```

[top](#index)