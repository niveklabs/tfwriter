# github_branch_protection

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_branch_protection" {
  source = "./modules/github/r/github_branch_protection"

  # allows_deletions - (optional) is a type of bool
  allows_deletions = null
  # allows_force_pushes - (optional) is a type of bool
  allows_force_pushes = null
  # enforce_admins - (optional) is a type of bool
  enforce_admins = null
  # pattern - (required) is a type of string
  pattern = null
  # push_restrictions - (optional) is a type of set of string
  push_restrictions = []
  # repository_id - (required) is a type of string
  repository_id = null
  # require_signed_commits - (optional) is a type of bool
  require_signed_commits = null

  required_pull_request_reviews = [{
    dismiss_stale_reviews           = null
    dismissal_restrictions          = []
    require_code_owner_reviews      = null
    required_approving_review_count = null
  }]

  required_status_checks = [{
    contexts = []
    strict   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allows_deletions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allows_force_pushes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enforce_admins" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "pattern" {
  description = "(required)"
  type        = string
}

variable "push_restrictions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "repository_id" {
  description = "(required) - Node ID or name of repository"
  type        = string
}

variable "require_signed_commits" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "required_pull_request_reviews" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dismiss_stale_reviews           = bool
      dismissal_restrictions          = set(string)
      require_code_owner_reviews      = bool
      required_approving_review_count = number
    }
  ))
  default = []
}

variable "required_status_checks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      contexts = set(string)
      strict   = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "github_branch_protection" "this" {
  # allows_deletions - (optional) is a type of bool
  allows_deletions = var.allows_deletions
  # allows_force_pushes - (optional) is a type of bool
  allows_force_pushes = var.allows_force_pushes
  # enforce_admins - (optional) is a type of bool
  enforce_admins = var.enforce_admins
  # pattern - (required) is a type of string
  pattern = var.pattern
  # push_restrictions - (optional) is a type of set of string
  push_restrictions = var.push_restrictions
  # repository_id - (required) is a type of string
  repository_id = var.repository_id
  # require_signed_commits - (optional) is a type of bool
  require_signed_commits = var.require_signed_commits

  dynamic "required_pull_request_reviews" {
    for_each = var.required_pull_request_reviews
    content {
      # dismiss_stale_reviews - (optional) is a type of bool
      dismiss_stale_reviews = required_pull_request_reviews.value["dismiss_stale_reviews"]
      # dismissal_restrictions - (optional) is a type of set of string
      dismissal_restrictions = required_pull_request_reviews.value["dismissal_restrictions"]
      # require_code_owner_reviews - (optional) is a type of bool
      require_code_owner_reviews = required_pull_request_reviews.value["require_code_owner_reviews"]
      # required_approving_review_count - (optional) is a type of number
      required_approving_review_count = required_pull_request_reviews.value["required_approving_review_count"]
    }
  }

  dynamic "required_status_checks" {
    for_each = var.required_status_checks
    content {
      # contexts - (optional) is a type of set of string
      contexts = required_status_checks.value["contexts"]
      # strict - (optional) is a type of bool
      strict = required_status_checks.value["strict"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = github_branch_protection.this.id
}

output "this" {
  value = github_branch_protection.this
}
```

[top](#index)