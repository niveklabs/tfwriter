# prismacloud_alert_rule

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/prismacloud/d/prismacloud_alert_rule"

  # name - (optional) is a type of string
  name = null
  # policy_scan_config_id - (optional) is a type of string
  policy_scan_config_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Rule/Scan name"
  type        = string
  default     = null
}

variable "policy_scan_config_id" {
  description = "(optional) - Policy scan config ID"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_alert_rule" "this" {
  # name - (optional) is a type of string
  name = var.name
  # policy_scan_config_id - (optional) is a type of string
  policy_scan_config_id = var.policy_scan_config_id
}
```

[top](#index)

### Outputs

```terraform
output "allow_auto_remediate" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.allow_auto_remediate
}

output "delay_notification_ms" {
  description = "returns a number"
  value       = data.prismacloud_alert_rule.this.delay_notification_ms
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_alert_rule.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.enabled
}

output "excluded_policies" {
  description = "returns a list of string"
  value       = data.prismacloud_alert_rule.this.excluded_policies
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_alert_rule.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_alert_rule.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = data.prismacloud_alert_rule.this.last_modified_on
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_alert_rule.this.name
}

output "notification_channels" {
  description = "returns a list of string"
  value       = data.prismacloud_alert_rule.this.notification_channels
}

output "notification_config" {
  description = "returns a list of object"
  value       = data.prismacloud_alert_rule.this.notification_config
}

output "notify_on_dismissed" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.notify_on_dismissed
}

output "notify_on_open" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.notify_on_open
}

output "notify_on_resolved" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.notify_on_resolved
}

output "notify_on_snoozed" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.notify_on_snoozed
}

output "open_alerts_count" {
  description = "returns a number"
  value       = data.prismacloud_alert_rule.this.open_alerts_count
}

output "owner" {
  description = "returns a string"
  value       = data.prismacloud_alert_rule.this.owner
}

output "policies" {
  description = "returns a set of string"
  value       = data.prismacloud_alert_rule.this.policies
}

output "policy_labels" {
  description = "returns a list of string"
  value       = data.prismacloud_alert_rule.this.policy_labels
}

output "policy_scan_config_id" {
  description = "returns a string"
  value       = data.prismacloud_alert_rule.this.policy_scan_config_id
}

output "read_only" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.read_only
}

output "scan_all" {
  description = "returns a bool"
  value       = data.prismacloud_alert_rule.this.scan_all
}

output "target" {
  description = "returns a list of object"
  value       = data.prismacloud_alert_rule.this.target
}

output "this" {
  value = prismacloud_alert_rule.this
}
```

[top](#index)