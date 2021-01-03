# lacework_alert_channel_aws_cloudwatch

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
module "lacework_alert_channel_aws_cloudwatch" {
  source = "./modules/lacework/r/lacework_alert_channel_aws_cloudwatch"

  # enabled - (optional) is a type of bool
  enabled = null
  # event_bus_arn - (required) is a type of string
  event_bus_arn = null
  # group_issues_by - (optional) is a type of string
  group_issues_by = null
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

variable "event_bus_arn" {
  description = "(required)"
  type        = string
}

variable "group_issues_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_aws_cloudwatch" "this" {
  enabled         = var.enabled
  event_bus_arn   = var.event_bus_arn
  group_issues_by = var.group_issues_by
  name            = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_cloudwatch.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_cloudwatch.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_cloudwatch.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_cloudwatch.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_aws_cloudwatch.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_aws_cloudwatch.this.type_name
}

output "this" {
  value = lacework_alert_channel_aws_cloudwatch.this
}
```

[top](#index)