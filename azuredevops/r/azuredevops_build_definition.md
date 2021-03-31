# azuredevops_build_definition

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
module "azuredevops_build_definition" {
  source = "./modules/azuredevops/r/azuredevops_build_definition"

  # agent_pool_name - (optional) is a type of string
  agent_pool_name = null
  # name - (optional) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # project_id - (required) is a type of string
  project_id = null
  # variable_groups - (optional) is a type of set of number
  variable_groups = []

  ci_trigger = [{
    override = [{
      batch = null
      branch_filter = [{
        exclude = []
        include = []
      }]
      max_concurrent_builds_per_branch = null
      path_filter = [{
        exclude = []
        include = []
      }]
      polling_interval = null
      polling_job_id   = null
    }]
    use_yaml = null
  }]

  pull_request_trigger = [{
    comment_required = null
    forks = [{
      enabled       = null
      share_secrets = null
    }]
    initial_branch = null
    override = [{
      auto_cancel = null
      branch_filter = [{
        exclude = []
        include = []
      }]
      path_filter = [{
        exclude = []
        include = []
      }]
    }]
    use_yaml = null
  }]

  repository = [{
    branch_name           = null
    github_enterprise_url = null
    repo_id               = null
    repo_type             = null
    report_build_status   = null
    service_connection_id = null
    yml_path              = null
  }]

  variable = [{
    allow_override = null
    is_secret      = null
    name           = null
    secret_value   = null
    value          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "agent_pool_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "variable_groups" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "ci_trigger" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      override = list(object(
        {
          batch = bool
          branch_filter = set(object(
            {
              exclude = set(string)
              include = set(string)
            }
          ))
          max_concurrent_builds_per_branch = number
          path_filter = set(object(
            {
              exclude = set(string)
              include = set(string)
            }
          ))
          polling_interval = number
          polling_job_id   = string
        }
      ))
      use_yaml = bool
    }
  ))
  default = []
}

variable "pull_request_trigger" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comment_required = string
      forks = list(object(
        {
          enabled       = bool
          share_secrets = bool
        }
      ))
      initial_branch = string
      override = list(object(
        {
          auto_cancel = bool
          branch_filter = set(object(
            {
              exclude = set(string)
              include = set(string)
            }
          ))
          path_filter = set(object(
            {
              exclude = set(string)
              include = set(string)
            }
          ))
        }
      ))
      use_yaml = bool
    }
  ))
  default = []
}

variable "repository" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      branch_name           = string
      github_enterprise_url = string
      repo_id               = string
      repo_type             = string
      report_build_status   = bool
      service_connection_id = string
      yml_path              = string
    }
  ))
}

variable "variable" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allow_override = bool
      is_secret      = bool
      name           = string
      secret_value   = string
      value          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_build_definition" "this" {
  agent_pool_name = var.agent_pool_name
  name            = var.name
  path            = var.path
  project_id      = var.project_id
  variable_groups = var.variable_groups

  dynamic "ci_trigger" {
    for_each = var.ci_trigger
    content {
      use_yaml = ci_trigger.value["use_yaml"]

      dynamic "override" {
        for_each = ci_trigger.value.override
        content {
          batch                            = override.value["batch"]
          max_concurrent_builds_per_branch = override.value["max_concurrent_builds_per_branch"]
          polling_interval                 = override.value["polling_interval"]

          dynamic "branch_filter" {
            for_each = override.value.branch_filter
            content {
              exclude = branch_filter.value["exclude"]
              include = branch_filter.value["include"]
            }
          }

          dynamic "path_filter" {
            for_each = override.value.path_filter
            content {
              exclude = path_filter.value["exclude"]
              include = path_filter.value["include"]
            }
          }

        }
      }

    }
  }

  dynamic "pull_request_trigger" {
    for_each = var.pull_request_trigger
    content {
      comment_required = pull_request_trigger.value["comment_required"]
      initial_branch   = pull_request_trigger.value["initial_branch"]
      use_yaml         = pull_request_trigger.value["use_yaml"]

      dynamic "forks" {
        for_each = pull_request_trigger.value.forks
        content {
          enabled       = forks.value["enabled"]
          share_secrets = forks.value["share_secrets"]
        }
      }

      dynamic "override" {
        for_each = pull_request_trigger.value.override
        content {
          auto_cancel = override.value["auto_cancel"]

          dynamic "branch_filter" {
            for_each = override.value.branch_filter
            content {
              exclude = branch_filter.value["exclude"]
              include = branch_filter.value["include"]
            }
          }

          dynamic "path_filter" {
            for_each = override.value.path_filter
            content {
              exclude = path_filter.value["exclude"]
              include = path_filter.value["include"]
            }
          }

        }
      }

    }
  }

  dynamic "repository" {
    for_each = var.repository
    content {
      branch_name           = repository.value["branch_name"]
      github_enterprise_url = repository.value["github_enterprise_url"]
      repo_id               = repository.value["repo_id"]
      repo_type             = repository.value["repo_type"]
      report_build_status   = repository.value["report_build_status"]
      service_connection_id = repository.value["service_connection_id"]
      yml_path              = repository.value["yml_path"]
    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      allow_override = variable.value["allow_override"]
      is_secret      = variable.value["is_secret"]
      name           = variable.value["name"]
      secret_value   = variable.value["secret_value"]
      value          = variable.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_build_definition.this.id
}

output "revision" {
  description = "returns a number"
  value       = azuredevops_build_definition.this.revision
}

output "this" {
  value = azuredevops_build_definition.this
}
```

[top](#index)