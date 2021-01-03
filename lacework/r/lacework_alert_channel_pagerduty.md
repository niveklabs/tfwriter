# lacework_alert_channel_pagerduty

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.2.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_alert_channel_pagerduty" {
  source = "./modules/lacework/r/lacework_alert_channel_pagerduty"

  # enabled - (optional) is a type of bool
  enabled = null
  # integration_key - (required) is a type of string
  integration_key = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "integration_key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_pagerduty" "this" {
  enabled         = var.enabled
  integration_key = var.integration_key
  name            = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_pagerduty.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_pagerduty.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_pagerduty.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_pagerduty.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_pagerduty.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_pagerduty.this.type_name
}

output "this" {
  value = lacework_alert_channel_pagerduty.this
}
```

[top](#index)