# azuredevops_branch_policy_merge_types

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
module "azuredevops_branch_policy_merge_types" {
  source = "./modules/azuredevops/r/azuredevops_branch_policy_merge_types"

  # blocking - (optional) is a type of bool
  blocking = null
  # enabled - (optional) is a type of bool
  enabled = null
  # project_id - (required) is a type of string
  project_id = null

  settings = [{
    allow_basic_no_fast_forward   = null
    allow_rebase_and_fast_forward = null
    allow_rebase_with_merge       = null
    allow_squash                  = null
    scope = [{
      match_type     = null
      repository_id  = null
      repository_ref = null
    }]
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
      allow_basic_no_fast_forward   = bool
      allow_rebase_and_fast_forward = bool
      allow_rebase_with_merge       = bool
      allow_squash                  = bool
      scope = list(object(
        {
          match_type     = string
          repository_id  = string
          repository_ref = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_branch_policy_merge_types" "this" {
  # blocking - (optional) is a type of bool
  blocking = var.blocking
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "settings" {
    for_each = var.settings
    content {
      # allow_basic_no_fast_forward - (optional) is a type of bool
      allow_basic_no_fast_forward = settings.value["allow_basic_no_fast_forward"]
      # allow_rebase_and_fast_forward - (optional) is a type of bool
      allow_rebase_and_fast_forward = settings.value["allow_rebase_and_fast_forward"]
      # allow_rebase_with_merge - (optional) is a type of bool
      allow_rebase_with_merge = settings.value["allow_rebase_with_merge"]
      # allow_squash - (optional) is a type of bool
      allow_squash = settings.value["allow_squash"]

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
  value       = azuredevops_branch_policy_merge_types.this.id
}

output "this" {
  value = azuredevops_branch_policy_merge_types.this
}
```

[top](#index)