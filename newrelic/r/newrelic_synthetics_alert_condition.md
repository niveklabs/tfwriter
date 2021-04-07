# newrelic_synthetics_alert_condition

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
module "newrelic_synthetics_alert_condition" {
  source = "./modules/newrelic/r/newrelic_synthetics_alert_condition"

  # enabled - (optional) is a type of bool
  enabled = null
  # monitor_id - (required) is a type of string
  monitor_id = null
  # name - (required) is a type of string
  name = null
  # policy_id - (required) is a type of number
  policy_id = null
  # runbook_url - (optional) is a type of string
  runbook_url = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Set whether to enable the alert condition. Defaults to true."
  type        = bool
  default     = null
}

variable "monitor_id" {
  description = "(required) - The ID of the Synthetics monitor to be referenced in the alert condition."
  type        = string
}

variable "name" {
  description = "(required) - The title of this condition."
  type        = string
}

variable "policy_id" {
  description = "(required) - The ID of the policy where this condition should be used."
  type        = number
}

variable "runbook_url" {
  description = "(optional) - Runbook URL to display in notifications."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_synthetics_alert_condition" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # monitor_id - (required) is a type of string
  monitor_id = var.monitor_id
  # name - (required) is a type of string
  name = var.name
  # policy_id - (required) is a type of number
  policy_id = var.policy_id
  # runbook_url - (optional) is a type of string
  runbook_url = var.runbook_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_synthetics_alert_condition.this.id
}

output "this" {
  value = newrelic_synthetics_alert_condition.this
}
```

[top](#index)