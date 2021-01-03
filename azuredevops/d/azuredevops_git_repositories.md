# azuredevops_git_repositories

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azuredevops_git_repositories" {
  source = "./modules/azuredevops/d/azuredevops_git_repositories"

  # include_hidden - (optional) is a type of bool
  include_hidden = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "include_hidden" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_git_repositories" "this" {
  include_hidden = var.include_hidden
  name           = var.name
  project_id     = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azuredevops_git_repositories.this.id
}

output "repositories" {
  description = "returns a list of object"
  value       = data.azuredevops_git_repositories.this.repositories
}

output "this" {
  value = azuredevops_git_repositories.this
}
```

[top](#index)