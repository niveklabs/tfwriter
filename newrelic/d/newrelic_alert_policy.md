# newrelic_alert_policy

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "newrelic_alert_policy" {
  source = "./modules/newrelic/d/newrelic_alert_policy"

  # account_id - (optional) is a type of number
  account_id = null
  # incident_preference - (optional) is a type of string
  incident_preference = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The New Relic account ID to operate on."
  type        = number
  default     = null
}

variable "incident_preference" {
  description = "(optional) - The rollup strategy for the policy. Options include: `PER_POLICY`, `PER_CONDITION`, or `PER_CONDITION_AND_TARGET`. The default is `PER_POLICY`."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the alert policy in New Relic."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_alert_policy" "this" {
  account_id          = var.account_id
  incident_preference = var.incident_preference
  name                = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = data.newrelic_alert_policy.this.account_id
}

output "created_at" {
  description = "returns a string"
  value       = data.newrelic_alert_policy.this.created_at
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_alert_policy.this.id
}

output "updated_at" {
  description = "returns a string"
  value       = data.newrelic_alert_policy.this.updated_at
}

output "this" {
  value = newrelic_alert_policy.this
}
```

[top](#index)