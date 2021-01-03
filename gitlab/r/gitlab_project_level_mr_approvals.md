# gitlab_project_level_mr_approvals

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
    gitlab = ">= 3.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_project_level_mr_approvals" {
  source = "./modules/gitlab/r/gitlab_project_level_mr_approvals"

  # disable_overriding_approvers_per_merge_request - (optional) is a type of bool
  disable_overriding_approvers_per_merge_request = null
  # merge_requests_author_approval - (optional) is a type of bool
  merge_requests_author_approval = null
  # merge_requests_disable_committers_approval - (optional) is a type of bool
  merge_requests_disable_committers_approval = null
  # project_id - (required) is a type of number
  project_id = null
  # reset_approvals_on_push - (optional) is a type of bool
  reset_approvals_on_push = null
}
```

[top](#index)

### Variables

```terraform
variable "disable_overriding_approvers_per_merge_request" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "merge_requests_author_approval" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "merge_requests_disable_committers_approval" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = number
}

variable "reset_approvals_on_push" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_level_mr_approvals" "this" {
  disable_overriding_approvers_per_merge_request = var.disable_overriding_approvers_per_merge_request
  merge_requests_author_approval                 = var.merge_requests_author_approval
  merge_requests_disable_committers_approval     = var.merge_requests_disable_committers_approval
  project_id                                     = var.project_id
  reset_approvals_on_push                        = var.reset_approvals_on_push
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_level_mr_approvals.this.id
}

output "this" {
  value = gitlab_project_level_mr_approvals.this
}
```

[top](#index)