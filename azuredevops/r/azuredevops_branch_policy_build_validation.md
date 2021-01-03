# azuredevops_branch_policy_build_validation

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
module "azuredevops_branch_policy_build_validation" {
  source = "./modules/azuredevops/r/azuredevops_branch_policy_build_validation"

  # blocking - (optional) is a type of bool
  blocking = null
  # enabled - (optional) is a type of bool
  enabled = null
  # project_id - (required) is a type of string
  project_id = null

  settings = [{
    build_definition_id         = null
    display_name                = null
    filename_patterns           = []
    manual_queue_only           = null
    queue_on_source_update_only = null
    scope = [{
      match_type     = null
      repository_id  = null
      repository_ref = null
    }]
    valid_duration = null
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
      build_definition_id         = number
      display_name                = string
      filename_patterns           = set(string)
      manual_queue_only           = bool
      queue_on_source_update_only = bool
      scope = list(object(
        {
          match_type     = string
          repository_id  = string
          repository_ref = string
        }
      ))
      valid_duration = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_branch_policy_build_validation" "this" {
  blocking   = var.blocking
  enabled    = var.enabled
  project_id = var.project_id

  dynamic "settings" {
    for_each = var.settings
    content {
      build_definition_id         = settings.value["build_definition_id"]
      display_name                = settings.value["display_name"]
      filename_patterns           = settings.value["filename_patterns"]
      manual_queue_only           = settings.value["manual_queue_only"]
      queue_on_source_update_only = settings.value["queue_on_source_update_only"]
      valid_duration              = settings.value["valid_duration"]

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
  value       = azuredevops_branch_policy_build_validation.this.id
}

output "this" {
  value = azuredevops_branch_policy_build_validation.this
}
```

[top](#index)