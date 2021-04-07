# github_branch_protection_v3

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
module "github_branch_protection_v3" {
  source = "./modules/github/r/github_branch_protection_v3"

  # branch - (required) is a type of string
  branch = null
  # enforce_admins - (optional) is a type of bool
  enforce_admins = null
  # repository - (required) is a type of string
  repository = null
  # require_signed_commits - (optional) is a type of bool
  require_signed_commits = null

  required_pull_request_reviews = [{
    dismiss_stale_reviews           = null
    dismissal_teams                 = []
    dismissal_users                 = []
    include_admins                  = null
    require_code_owner_reviews      = null
    required_approving_review_count = null
  }]

  required_status_checks = [{
    contexts       = []
    include_admins = null
    strict         = null
  }]

  restrictions = [{
    apps  = []
    teams = []
    users = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "branch" {
  description = "(required)"
  type        = string
}

variable "enforce_admins" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "require_signed_commits" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "required_pull_request_reviews" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dismiss_stale_reviews           = bool
      dismissal_teams                 = set(string)
      dismissal_users                 = set(string)
      include_admins                  = bool
      require_code_owner_reviews      = bool
      required_approving_review_count = number
    }
  ))
  default = []
}

variable "required_status_checks" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      contexts       = set(string)
      include_admins = bool
      strict         = bool
    }
  ))
  default = []
}

variable "restrictions" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      apps  = set(string)
      teams = set(string)
      users = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "github_branch_protection_v3" "this" {
  # branch - (required) is a type of string
  branch = var.branch
  # enforce_admins - (optional) is a type of bool
  enforce_admins = var.enforce_admins
  # repository - (required) is a type of string
  repository = var.repository
  # require_signed_commits - (optional) is a type of bool
  require_signed_commits = var.require_signed_commits

  dynamic "required_pull_request_reviews" {
    for_each = var.required_pull_request_reviews
    content {
      # dismiss_stale_reviews - (optional) is a type of bool
      dismiss_stale_reviews = required_pull_request_reviews.value["dismiss_stale_reviews"]
      # dismissal_teams - (optional) is a type of set of string
      dismissal_teams = required_pull_request_reviews.value["dismissal_teams"]
      # dismissal_users - (optional) is a type of set of string
      dismissal_users = required_pull_request_reviews.value["dismissal_users"]
      # include_admins - (optional) is a type of bool
      include_admins = required_pull_request_reviews.value["include_admins"]
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
      # include_admins - (optional) is a type of bool
      include_admins = required_status_checks.value["include_admins"]
      # strict - (optional) is a type of bool
      strict = required_status_checks.value["strict"]
    }
  }

  dynamic "restrictions" {
    for_each = var.restrictions
    content {
      # apps - (optional) is a type of set of string
      apps = restrictions.value["apps"]
      # teams - (optional) is a type of set of string
      teams = restrictions.value["teams"]
      # users - (optional) is a type of set of string
      users = restrictions.value["users"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_branch_protection_v3.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_branch_protection_v3.this.id
}

output "this" {
  value = github_branch_protection_v3.this
}
```

[top](#index)