# lacework_alert_channel_slack

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
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_alert_channel_slack" {
  source = "./modules/lacework/r/lacework_alert_channel_slack"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # slack_url - (required) is a type of string
  slack_url = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "slack_url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_slack" "this" {
  enabled   = var.enabled
  name      = var.name
  slack_url = var.slack_url
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_slack.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_slack.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_slack.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_slack.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_slack.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_slack.this.type_name
}

output "this" {
  value = lacework_alert_channel_slack.this
}
```

[top](#index)