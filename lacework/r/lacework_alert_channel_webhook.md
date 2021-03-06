# lacework_alert_channel_webhook

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
module "lacework_alert_channel_webhook" {
  source = "./modules/lacework/r/lacework_alert_channel_webhook"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # webhook_url - (required) is a type of string
  webhook_url = null
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

variable "webhook_url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_webhook" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # webhook_url - (required) is a type of string
  webhook_url = var.webhook_url
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_webhook.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_webhook.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_webhook.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_webhook.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_webhook.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_webhook.this.type_name
}

output "this" {
  value = lacework_alert_channel_webhook.this
}
```

[top](#index)