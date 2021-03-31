# newrelic_alert_policy

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
module "newrelic_alert_policy" {
  source = "./modules/newrelic/r/newrelic_alert_policy"

  # account_id - (optional) is a type of number
  account_id = null
  # channel_ids - (optional) is a type of list of number
  channel_ids = []
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

variable "channel_ids" {
  description = "(optional) - An array of channel IDs (integers) to assign to the policy. Adding or removing channel IDs from this array will result in a new alert policy resource being created and the old one being destroyed. Also note that channel IDs cannot be imported via terraform import."
  type        = list(number)
  default     = null
}

variable "incident_preference" {
  description = "(optional) - The rollup strategy for the policy. Options include: PER_POLICY, PER_CONDITION, or PER_CONDITION_AND_TARGET. The default is PER_POLICY."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the policy."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_alert_policy" "this" {
  account_id          = var.account_id
  channel_ids         = var.channel_ids
  incident_preference = var.incident_preference
  name                = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_alert_policy.this.account_id
}

output "id" {
  description = "returns a string"
  value       = newrelic_alert_policy.this.id
}

output "this" {
  value = newrelic_alert_policy.this
}
```

[top](#index)