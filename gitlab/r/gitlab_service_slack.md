# gitlab_service_slack

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
module "gitlab_service_slack" {
  source = "./modules/gitlab/r/gitlab_service_slack"

  # branches_to_be_notified - (optional) is a type of string
  branches_to_be_notified = null
  # confidential_issue_channel - (optional) is a type of string
  confidential_issue_channel = null
  # confidential_issues_events - (optional) is a type of bool
  confidential_issues_events = null
  # confidential_note_events - (optional) is a type of bool
  confidential_note_events = null
  # issue_channel - (optional) is a type of string
  issue_channel = null
  # issues_events - (optional) is a type of bool
  issues_events = null
  # merge_request_channel - (optional) is a type of string
  merge_request_channel = null
  # merge_requests_events - (optional) is a type of bool
  merge_requests_events = null
  # note_channel - (optional) is a type of string
  note_channel = null
  # note_events - (optional) is a type of bool
  note_events = null
  # notify_only_broken_pipelines - (optional) is a type of bool
  notify_only_broken_pipelines = null
  # notify_only_default_branch - (optional) is a type of bool
  notify_only_default_branch = null
  # pipeline_channel - (optional) is a type of string
  pipeline_channel = null
  # pipeline_events - (optional) is a type of bool
  pipeline_events = null
  # project - (required) is a type of string
  project = null
  # push_channel - (optional) is a type of string
  push_channel = null
  # push_events - (optional) is a type of bool
  push_events = null
  # tag_push_channel - (optional) is a type of string
  tag_push_channel = null
  # tag_push_events - (optional) is a type of bool
  tag_push_events = null
  # username - (optional) is a type of string
  username = null
  # webhook - (required) is a type of string
  webhook = null
  # wiki_page_channel - (optional) is a type of string
  wiki_page_channel = null
  # wiki_page_events - (optional) is a type of bool
  wiki_page_events = null
}
```

[top](#index)

### Variables

```terraform
variable "branches_to_be_notified" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "confidential_issue_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "confidential_issues_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "confidential_note_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "issue_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "issues_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "merge_request_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "merge_requests_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "note_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "note_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notify_only_broken_pipelines" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notify_only_default_branch" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "pipeline_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pipeline_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "push_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "push_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tag_push_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag_push_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webhook" {
  description = "(required)"
  type        = string
}

variable "wiki_page_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wiki_page_events" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_service_slack" "this" {
  branches_to_be_notified      = var.branches_to_be_notified
  confidential_issue_channel   = var.confidential_issue_channel
  confidential_issues_events   = var.confidential_issues_events
  confidential_note_events     = var.confidential_note_events
  issue_channel                = var.issue_channel
  issues_events                = var.issues_events
  merge_request_channel        = var.merge_request_channel
  merge_requests_events        = var.merge_requests_events
  note_channel                 = var.note_channel
  note_events                  = var.note_events
  notify_only_broken_pipelines = var.notify_only_broken_pipelines
  notify_only_default_branch   = var.notify_only_default_branch
  pipeline_channel             = var.pipeline_channel
  pipeline_events              = var.pipeline_events
  project                      = var.project
  push_channel                 = var.push_channel
  push_events                  = var.push_events
  tag_push_channel             = var.tag_push_channel
  tag_push_events              = var.tag_push_events
  username                     = var.username
  webhook                      = var.webhook
  wiki_page_channel            = var.wiki_page_channel
  wiki_page_events             = var.wiki_page_events
}
```

[top](#index)

### Outputs

```terraform
output "branches_to_be_notified" {
  description = "returns a string"
  value       = gitlab_service_slack.this.branches_to_be_notified
}

output "confidential_issues_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.confidential_issues_events
}

output "confidential_note_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.confidential_note_events
}

output "id" {
  description = "returns a string"
  value       = gitlab_service_slack.this.id
}

output "issues_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.issues_events
}

output "job_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.job_events
}

output "merge_requests_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.merge_requests_events
}

output "note_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.note_events
}

output "notify_only_broken_pipelines" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.notify_only_broken_pipelines
}

output "notify_only_default_branch" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.notify_only_default_branch
}

output "pipeline_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.pipeline_events
}

output "push_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.push_events
}

output "tag_push_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.tag_push_events
}

output "wiki_page_events" {
  description = "returns a bool"
  value       = gitlab_service_slack.this.wiki_page_events
}

output "this" {
  value = gitlab_service_slack.this
}
```

[top](#index)