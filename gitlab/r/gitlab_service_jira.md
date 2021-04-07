# gitlab_service_jira

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_service_jira" {
  source = "./modules/gitlab/r/gitlab_service_jira"

  # comment_on_event_enabled - (optional) is a type of bool
  comment_on_event_enabled = null
  # commit_events - (optional) is a type of bool
  commit_events = null
  # jira_issue_transition_id - (optional) is a type of string
  jira_issue_transition_id = null
  # merge_requests_events - (optional) is a type of bool
  merge_requests_events = null
  # password - (required) is a type of string
  password = null
  # project - (required) is a type of string
  project = null
  # project_key - (optional) is a type of string
  project_key = null
  # url - (required) is a type of string
  url = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "comment_on_event_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "commit_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "jira_issue_transition_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "merge_requests_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "project_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
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
resource "gitlab_service_jira" "this" {
  # comment_on_event_enabled - (optional) is a type of bool
  comment_on_event_enabled = var.comment_on_event_enabled
  # commit_events - (optional) is a type of bool
  commit_events = var.commit_events
  # jira_issue_transition_id - (optional) is a type of string
  jira_issue_transition_id = var.jira_issue_transition_id
  # merge_requests_events - (optional) is a type of bool
  merge_requests_events = var.merge_requests_events
  # password - (required) is a type of string
  password = var.password
  # project - (required) is a type of string
  project = var.project
  # project_key - (optional) is a type of string
  project_key = var.project_key
  # url - (required) is a type of string
  url = var.url
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "active" {
  description = "returns a bool"
  value       = gitlab_service_jira.this.active
}

output "comment_on_event_enabled" {
  description = "returns a bool"
  value       = gitlab_service_jira.this.comment_on_event_enabled
}

output "commit_events" {
  description = "returns a bool"
  value       = gitlab_service_jira.this.commit_events
}

output "created_at" {
  description = "returns a string"
  value       = gitlab_service_jira.this.created_at
}

output "id" {
  description = "returns a string"
  value       = gitlab_service_jira.this.id
}

output "merge_requests_events" {
  description = "returns a bool"
  value       = gitlab_service_jira.this.merge_requests_events
}

output "title" {
  description = "returns a string"
  value       = gitlab_service_jira.this.title
}

output "updated_at" {
  description = "returns a string"
  value       = gitlab_service_jira.this.updated_at
}

output "this" {
  value = gitlab_service_jira.this
}
```

[top](#index)