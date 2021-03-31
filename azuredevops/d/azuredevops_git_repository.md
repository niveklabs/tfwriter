# azuredevops_git_repository

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
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_git_repository" {
  source = "./modules/azuredevops/d/azuredevops_git_repository"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_git_repository" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "default_branch" {
  description = "returns a string"
  value       = data.azuredevops_git_repository.this.default_branch
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_git_repository.this.id
}

output "is_fork" {
  description = "returns a bool"
  value       = data.azuredevops_git_repository.this.is_fork
}

output "remote_url" {
  description = "returns a string"
  value       = data.azuredevops_git_repository.this.remote_url
}

output "size" {
  description = "returns a number"
  value       = data.azuredevops_git_repository.this.size
}

output "ssh_url" {
  description = "returns a string"
  value       = data.azuredevops_git_repository.this.ssh_url
}

output "url" {
  description = "returns a string"
  value       = data.azuredevops_git_repository.this.url
}

output "web_url" {
  description = "returns a string"
  value       = data.azuredevops_git_repository.this.web_url
}

output "this" {
  value = azuredevops_git_repository.this
}
```

[top](#index)