# lacework_alert_channel_jira_server

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
module "lacework_alert_channel_jira_server" {
  source = "./modules/lacework/r/lacework_alert_channel_jira_server"

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
  # password - (required) is a type of string
  password = null
  # project_key - (required) is a type of string
  project_key = null
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

variable "password" {
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
resource "lacework_alert_channel_jira_server" "this" {
  custom_template_file = var.custom_template_file
  enabled              = var.enabled
  group_issues_by      = var.group_issues_by
  issue_type           = var.issue_type
  jira_url             = var.jira_url
  name                 = var.name
  password             = var.password
  project_key          = var.project_key
  username             = var.username
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_server.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_server.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_server.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_server.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_jira_server.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_jira_server.this.type_name
}

output "this" {
  value = lacework_alert_channel_jira_server.this
}
```

[top](#index)