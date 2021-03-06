# gitlab_project_hook

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
module "gitlab_project_hook" {
  source = "./modules/gitlab/r/gitlab_project_hook"

  # confidential_issues_events - (optional) is a type of bool
  confidential_issues_events = null
  # confidential_note_events - (optional) is a type of bool
  confidential_note_events = null
  # deployment_events - (optional) is a type of bool
  deployment_events = null
  # enable_ssl_verification - (optional) is a type of bool
  enable_ssl_verification = null
  # issues_events - (optional) is a type of bool
  issues_events = null
  # job_events - (optional) is a type of bool
  job_events = null
  # merge_requests_events - (optional) is a type of bool
  merge_requests_events = null
  # note_events - (optional) is a type of bool
  note_events = null
  # pipeline_events - (optional) is a type of bool
  pipeline_events = null
  # project - (required) is a type of string
  project = null
  # push_events - (optional) is a type of bool
  push_events = null
  # push_events_branch_filter - (optional) is a type of string
  push_events_branch_filter = null
  # tag_push_events - (optional) is a type of bool
  tag_push_events = null
  # token - (optional) is a type of string
  token = null
  # url - (required) is a type of string
  url = null
  # wiki_page_events - (optional) is a type of bool
  wiki_page_events = null
}
```

[top](#index)

### Variables

```terraform
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

variable "deployment_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ssl_verification" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "issues_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "job_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "merge_requests_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "note_events" {
  description = "(optional)"
  type        = bool
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

variable "push_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "push_events_branch_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag_push_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
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
resource "gitlab_project_hook" "this" {
  # confidential_issues_events - (optional) is a type of bool
  confidential_issues_events = var.confidential_issues_events
  # confidential_note_events - (optional) is a type of bool
  confidential_note_events = var.confidential_note_events
  # deployment_events - (optional) is a type of bool
  deployment_events = var.deployment_events
  # enable_ssl_verification - (optional) is a type of bool
  enable_ssl_verification = var.enable_ssl_verification
  # issues_events - (optional) is a type of bool
  issues_events = var.issues_events
  # job_events - (optional) is a type of bool
  job_events = var.job_events
  # merge_requests_events - (optional) is a type of bool
  merge_requests_events = var.merge_requests_events
  # note_events - (optional) is a type of bool
  note_events = var.note_events
  # pipeline_events - (optional) is a type of bool
  pipeline_events = var.pipeline_events
  # project - (required) is a type of string
  project = var.project
  # push_events - (optional) is a type of bool
  push_events = var.push_events
  # push_events_branch_filter - (optional) is a type of string
  push_events_branch_filter = var.push_events_branch_filter
  # tag_push_events - (optional) is a type of bool
  tag_push_events = var.tag_push_events
  # token - (optional) is a type of string
  token = var.token
  # url - (required) is a type of string
  url = var.url
  # wiki_page_events - (optional) is a type of bool
  wiki_page_events = var.wiki_page_events
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_hook.this.id
}

output "this" {
  value = gitlab_project_hook.this
}
```

[top](#index)