# azuredevops_git_repository

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
module "azuredevops_git_repository" {
  source = "./modules/azuredevops/r/azuredevops_git_repository"

  # default_branch - (optional) is a type of string
  default_branch = null
  # name - (required) is a type of string
  name = null
  # parent_repository_id - (optional) is a type of string
  parent_repository_id = null
  # project_id - (required) is a type of string
  project_id = null

  initialization = [{
    init_type   = null
    source_type = null
    source_url  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_branch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_repository_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "initialization" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      init_type   = string
      source_type = string
      source_url  = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_git_repository" "this" {
  # default_branch - (optional) is a type of string
  default_branch = var.default_branch
  # name - (required) is a type of string
  name = var.name
  # parent_repository_id - (optional) is a type of string
  parent_repository_id = var.parent_repository_id
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "initialization" {
    for_each = var.initialization
    content {
      # init_type - (required) is a type of string
      init_type = initialization.value["init_type"]
      # source_type - (optional) is a type of string
      source_type = initialization.value["source_type"]
      # source_url - (optional) is a type of string
      source_url = initialization.value["source_url"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_branch" {
  description = "returns a string"
  value       = azuredevops_git_repository.this.default_branch
}

output "id" {
  description = "returns a string"
  value       = azuredevops_git_repository.this.id
}

output "is_fork" {
  description = "returns a bool"
  value       = azuredevops_git_repository.this.is_fork
}

output "remote_url" {
  description = "returns a string"
  value       = azuredevops_git_repository.this.remote_url
}

output "size" {
  description = "returns a number"
  value       = azuredevops_git_repository.this.size
}

output "ssh_url" {
  description = "returns a string"
  value       = azuredevops_git_repository.this.ssh_url
}

output "url" {
  description = "returns a string"
  value       = azuredevops_git_repository.this.url
}

output "web_url" {
  description = "returns a string"
  value       = azuredevops_git_repository.this.web_url
}

output "this" {
  value = azuredevops_git_repository.this
}
```

[top](#index)