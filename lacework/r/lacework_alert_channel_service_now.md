# lacework_alert_channel_service_now

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
module "lacework_alert_channel_service_now" {
  source = "./modules/lacework/r/lacework_alert_channel_service_now"

  # custom_template_file - (optional) is a type of string
  custom_template_file = null
  # enabled - (optional) is a type of bool
  enabled = null
  # instance_url - (required) is a type of string
  instance_url = null
  # issue_grouping - (optional) is a type of string
  issue_grouping = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_template_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_url" {
  description = "(required)"
  type        = string
}

variable "issue_grouping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_service_now" "this" {
  custom_template_file = var.custom_template_file
  enabled              = var.enabled
  instance_url         = var.instance_url
  issue_grouping       = var.issue_grouping
  name                 = var.name
  password             = var.password
  username             = var.username
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_service_now.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_service_now.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_service_now.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_service_now.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_service_now.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_service_now.this.type_name
}

output "this" {
  value = lacework_alert_channel_service_now.this
}
```

[top](#index)