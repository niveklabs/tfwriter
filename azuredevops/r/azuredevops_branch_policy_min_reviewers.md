# azuredevops_branch_policy_min_reviewers

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_branch_policy_min_reviewers" {
  source = "./modules/azuredevops/r/azuredevops_branch_policy_min_reviewers"

  # blocking - (optional) is a type of bool
  blocking = null
  # enabled - (optional) is a type of bool
  enabled = null
  # project_id - (required) is a type of string
  project_id = null

  settings = [{
    allow_completion_with_rejects_or_waits = null
    last_pusher_cannot_approve             = null
    on_last_iteration_require_vote         = null
    on_push_reset_all_votes                = null
    on_push_reset_approved_votes           = null
    reviewer_count                         = null
    scope = [{
      match_type     = null
      repository_id  = null
      repository_ref = null
    }]
    submitter_can_vote = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "blocking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "settings" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      allow_completion_with_rejects_or_waits = bool
      last_pusher_cannot_approve             = bool
      on_last_iteration_require_vote         = bool
      on_push_reset_all_votes                = bool
      on_push_reset_approved_votes           = bool
      reviewer_count                         = number
      scope = list(object(
        {
          match_type     = string
          repository_id  = string
          repository_ref = string
        }
      ))
      submitter_can_vote = bool
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_branch_policy_min_reviewers" "this" {
  # blocking - (optional) is a type of bool
  blocking = var.blocking
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "settings" {
    for_each = var.settings
    content {
      # allow_completion_with_rejects_or_waits - (optional) is a type of bool
      allow_completion_with_rejects_or_waits = settings.value["allow_completion_with_rejects_or_waits"]
      # last_pusher_cannot_approve - (optional) is a type of bool
      last_pusher_cannot_approve = settings.value["last_pusher_cannot_approve"]
      # on_last_iteration_require_vote - (optional) is a type of bool
      on_last_iteration_require_vote = settings.value["on_last_iteration_require_vote"]
      # on_push_reset_all_votes - (optional) is a type of bool
      on_push_reset_all_votes = settings.value["on_push_reset_all_votes"]
      # on_push_reset_approved_votes - (optional) is a type of bool
      on_push_reset_approved_votes = settings.value["on_push_reset_approved_votes"]
      # reviewer_count - (optional) is a type of number
      reviewer_count = settings.value["reviewer_count"]
      # submitter_can_vote - (optional) is a type of bool
      submitter_can_vote = settings.value["submitter_can_vote"]

      dynamic "scope" {
        for_each = settings.value.scope
        content {
          # match_type - (optional) is a type of string
          match_type = scope.value["match_type"]
          # repository_id - (optional) is a type of string
          repository_id = scope.value["repository_id"]
          # repository_ref - (optional) is a type of string
          repository_ref = scope.value["repository_ref"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_branch_policy_min_reviewers.this.id
}

output "this" {
  value = azuredevops_branch_policy_min_reviewers.this
}
```

[top](#index)