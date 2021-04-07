# gitlab_service_pipelines_email

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
module "gitlab_service_pipelines_email" {
  source = "./modules/gitlab/r/gitlab_service_pipelines_email"

  # branches_to_be_notified - (optional) is a type of string
  branches_to_be_notified = null
  # notify_only_broken_pipelines - (optional) is a type of bool
  notify_only_broken_pipelines = null
  # project - (required) is a type of string
  project = null
  # recipients - (required) is a type of set of string
  recipients = []
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

variable "notify_only_broken_pipelines" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "recipients" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_service_pipelines_email" "this" {
  # branches_to_be_notified - (optional) is a type of string
  branches_to_be_notified = var.branches_to_be_notified
  # notify_only_broken_pipelines - (optional) is a type of bool
  notify_only_broken_pipelines = var.notify_only_broken_pipelines
  # project - (required) is a type of string
  project = var.project
  # recipients - (required) is a type of set of string
  recipients = var.recipients
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_service_pipelines_email.this.id
}

output "this" {
  value = gitlab_service_pipelines_email.this
}
```

[top](#index)