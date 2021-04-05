# prismacloud_alert_rule

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_alert_rule" {
  source = "./modules/prismacloud/r/prismacloud_alert_rule"

  # allow_auto_remediate - (optional) is a type of bool
  allow_auto_remediate = null
  # delay_notification_ms - (optional) is a type of number
  delay_notification_ms = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # excluded_policies - (optional) is a type of list of string
  excluded_policies = []
  # name - (required) is a type of string
  name = null
  # notify_on_dismissed - (optional) is a type of bool
  notify_on_dismissed = null
  # notify_on_open - (optional) is a type of bool
  notify_on_open = null
  # notify_on_resolved - (optional) is a type of bool
  notify_on_resolved = null
  # notify_on_snoozed - (optional) is a type of bool
  notify_on_snoozed = null
  # policies - (optional) is a type of set of string
  policies = []
  # policy_labels - (optional) is a type of list of string
  policy_labels = []
  # scan_all - (optional) is a type of bool
  scan_all = null

  notification_config = [{
    config_id    = null
    config_type  = null
    day_of_month = null
    days_of_week = [{
      day    = null
      offset = null
    }]
    detailed_report       = null
    enabled               = null
    frequency             = null
    frequency_from_r_rule = null
    hour_of_day           = null
    include_remediation   = null
    last_sent_ts          = null
    last_updated          = null
    r_rule_schedule       = null
    recipients            = []
    template_id           = null
    timezone_id           = null
    with_compression      = null
  }]

  target = [{
    account_groups    = []
    excluded_accounts = []
    regions           = []
    tags = [{
      key    = null
      values = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_auto_remediate" {
  description = "(optional) - Allow auto-remediation"
  type        = bool
  default     = null
}

variable "delay_notification_ms" {
  description = "(optional) - Delay notifications by the specified milliseconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Enabled"
  type        = bool
  default     = null
}

variable "excluded_policies" {
  description = "(optional) - List of policies to exclude from scan"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required) - Rule/Scan name"
  type        = string
}

variable "notify_on_dismissed" {
  description = "(optional) - Include dismissed alerts in notification"
  type        = bool
  default     = null
}

variable "notify_on_open" {
  description = "(optional) - Include open alerts in notification"
  type        = bool
  default     = null
}

variable "notify_on_resolved" {
  description = "(optional) - Include resolved alerts in notification"
  type        = bool
  default     = null
}

variable "notify_on_snoozed" {
  description = "(optional) - Include snoozed alerts in notification"
  type        = bool
  default     = null
}

variable "policies" {
  description = "(optional) - List of specific policies to scan"
  type        = set(string)
  default     = null
}

variable "policy_labels" {
  description = "(optional) - Policy labels"
  type        = list(string)
  default     = null
}

variable "scan_all" {
  description = "(optional) - Scan all policies"
  type        = bool
  default     = null
}

variable "notification_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config_id    = string
      config_type  = string
      day_of_month = number
      days_of_week = list(object(
        {
          day    = string
          offset = number
        }
      ))
      detailed_report       = bool
      enabled               = bool
      frequency             = string
      frequency_from_r_rule = string
      hour_of_day           = number
      include_remediation   = bool
      last_sent_ts          = number
      last_updated          = number
      r_rule_schedule       = string
      recipients            = list(string)
      template_id           = string
      timezone_id           = string
      with_compression      = bool
    }
  ))
  default = []
}

variable "target" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      account_groups    = list(string)
      excluded_accounts = list(string)
      regions           = list(string)
      tags = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_alert_rule" "this" {
  allow_auto_remediate  = var.allow_auto_remediate
  delay_notification_ms = var.delay_notification_ms
  description           = var.description
  enabled               = var.enabled
  excluded_policies     = var.excluded_policies
  name                  = var.name
  notify_on_dismissed   = var.notify_on_dismissed
  notify_on_open        = var.notify_on_open
  notify_on_resolved    = var.notify_on_resolved
  notify_on_snoozed     = var.notify_on_snoozed
  policies              = var.policies
  policy_labels         = var.policy_labels
  scan_all              = var.scan_all

  dynamic "notification_config" {
    for_each = var.notification_config
    content {
      config_id             = notification_config.value["config_id"]
      config_type           = notification_config.value["config_type"]
      day_of_month          = notification_config.value["day_of_month"]
      detailed_report       = notification_config.value["detailed_report"]
      enabled               = notification_config.value["enabled"]
      frequency             = notification_config.value["frequency"]
      frequency_from_r_rule = notification_config.value["frequency_from_r_rule"]
      hour_of_day           = notification_config.value["hour_of_day"]
      include_remediation   = notification_config.value["include_remediation"]
      r_rule_schedule       = notification_config.value["r_rule_schedule"]
      recipients            = notification_config.value["recipients"]
      template_id           = notification_config.value["template_id"]
      timezone_id           = notification_config.value["timezone_id"]
      with_compression      = notification_config.value["with_compression"]

      dynamic "days_of_week" {
        for_each = notification_config.value.days_of_week
        content {
          day    = days_of_week.value["day"]
          offset = days_of_week.value["offset"]
        }
      }

    }
  }

  dynamic "target" {
    for_each = var.target
    content {
      account_groups    = target.value["account_groups"]
      excluded_accounts = target.value["excluded_accounts"]
      regions           = target.value["regions"]

      dynamic "tags" {
        for_each = target.value.tags
        content {
          key    = tags.value["key"]
          values = tags.value["values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = prismacloud_alert_rule.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_alert_rule.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = prismacloud_alert_rule.this.last_modified_on
}

output "notification_channels" {
  description = "returns a list of string"
  value       = prismacloud_alert_rule.this.notification_channels
}

output "open_alerts_count" {
  description = "returns a number"
  value       = prismacloud_alert_rule.this.open_alerts_count
}

output "owner" {
  description = "returns a string"
  value       = prismacloud_alert_rule.this.owner
}

output "policy_scan_config_id" {
  description = "returns a string"
  value       = prismacloud_alert_rule.this.policy_scan_config_id
}

output "read_only" {
  description = "returns a bool"
  value       = prismacloud_alert_rule.this.read_only
}

output "this" {
  value = prismacloud_alert_rule.this
}
```

[top](#index)