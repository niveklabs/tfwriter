# newrelic_alert_policy_channel

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
module "newrelic_alert_policy_channel" {
  source = "./modules/newrelic/r/newrelic_alert_policy_channel"

  # channel_ids - (required) is a type of list of number
  channel_ids = []
  # policy_id - (required) is a type of number
  policy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "channel_ids" {
  description = "(required) - Array of channel IDs to apply to the specified policy. We recommended sorting channel IDs in ascending order to avoid drift your Terraform state."
  type        = list(number)
}

variable "policy_id" {
  description = "(required) - The ID of the policy."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_alert_policy_channel" "this" {
  channel_ids = var.channel_ids
  policy_id   = var.policy_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_alert_policy_channel.this.id
}

output "this" {
  value = newrelic_alert_policy_channel.this
}
```

[top](#index)