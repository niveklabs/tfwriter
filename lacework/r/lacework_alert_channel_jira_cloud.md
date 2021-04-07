# lacework_alert_channel_jira_cloud

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
module "lacework_alert_channel_jira_cloud" {
  source = "./modules/lacework/r/lacework_alert_channel_jira_cloud"

  # api_token - (required) is a type of string
  api_token = null
  # custom_template_file - (optional) is a type of string
  custom_template_file = null
  # enabled - (optional) is a type of bool
  enabled = null
  # group_issues_by - (optional) is a type of string
  group_issues_by = null
  # issue_type - (required) is a type of string
  issue_type = null
  # jira_url - (required) is a type of string
  jira_url = null
  # name - (required) is a type of string
  name = null
  # project_key - (required) is a type of string
  project_key = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "api_token" {
  description = "(required)"
  type        = string
}

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

variable "group_issues_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "issue_type" {
  description = "(required)"
  type        = string
}

variable "jira_url" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_key" {
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
resource "lacework_alert_channel_jira_cloud" "this" {
  # api_token - (required) is a type of string
  api_token = var.api_token
  # custom_template_file - (optional) is a type of string
  custom_template_file = var.custom_template_file
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # group_issues_by - (optional) is a type of string
  group_issues_by = var.group_issues_by
  # issue_type - (required) is a type of string
  issue_type = var.issue_type
  # jira_url - (required) is a type of string
  jira_url = var.jira_url
  # name - (required) is a type of string
  name = var.name
  # project_key - (required) is a type of string
  project_key = var.project_key
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_cloud.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_cloud.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_cloud.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_cloud.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_jira_cloud.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_cloud.this.type_name
}

output "this" {
  value = lacework_alert_channel_jira_cloud.this
}
```

[top](#index)