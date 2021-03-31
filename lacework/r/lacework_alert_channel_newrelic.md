# lacework_alert_channel_newrelic

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
module "lacework_alert_channel_newrelic" {
  source = "./modules/lacework/r/lacework_alert_channel_newrelic"

  # account_id - (required) is a type of number
  account_id = null
  # enabled - (optional) is a type of bool
  enabled = null
  # insert_key - (required) is a type of string
  insert_key = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = number
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "insert_key" {
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
resource "lacework_alert_channel_newrelic" "this" {
  account_id = var.account_id
  enabled    = var.enabled
  insert_key = var.insert_key
  name       = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_newrelic.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_newrelic.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_newrelic.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_newrelic.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_newrelic.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_newrelic.this.type_name
}

output "this" {
  value = lacework_alert_channel_newrelic.this
}
```

[top](#index)