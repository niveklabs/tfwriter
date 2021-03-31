# azuredevops_git_permissions

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
module "azuredevops_git_permissions" {
  source = "./modules/azuredevops/r/azuredevops_git_permissions"

  # branch_name - (optional) is a type of string
  branch_name = null
  # permissions - (required) is a type of map of string
  permissions = {}
  # principal - (required) is a type of string
  principal = null
  # project_id - (required) is a type of string
  project_id = null
  # replace - (optional) is a type of bool
  replace = null
  # repository_id - (optional) is a type of string
  repository_id = null
}
```

[top](#index)

### Variables

```terraform
variable "branch_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permissions" {
  description = "(required)"
  type        = map(string)
}

variable "principal" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "replace" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_git_permissions" "this" {
  branch_name   = var.branch_name
  permissions   = var.permissions
  principal     = var.principal
  project_id    = var.project_id
  replace       = var.replace
  repository_id = var.repository_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_git_permissions.this.id
}

output "this" {
  value = azuredevops_git_permissions.this
}
```

[top](#index)