# azuredevops_branch_policy_comment_resolution

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
    azuredevops = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_branch_policy_comment_resolution" {
  source = "./modules/azuredevops/r/azuredevops_branch_policy_comment_resolution"

  # blocking - (optional) is a type of bool
  blocking = null
  # enabled - (optional) is a type of bool
  enabled = null
  # project_id - (required) is a type of string
  project_id = null

  settings = [{
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
resource "azuredevops_branch_policy_comment_resolution" "this" {
  blocking   = var.blocking
  enabled    = var.enabled
  project_id = var.project_id

  dynamic "settings" {
    for_each = var.settings
    content {

      dynamic "scope" {
        for_each = settings.value.scope
        content {
          match_type     = scope.value["match_type"]
          repository_id  = scope.value["repository_id"]
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
  value       = azuredevops_branch_policy_comment_resolution.this.id
}

output "this" {
  value = azuredevops_branch_policy_comment_resolution.this
}
```

[top](#index)