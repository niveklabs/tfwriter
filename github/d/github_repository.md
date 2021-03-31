# github_repository

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "github_repository" {
  source = "./modules/github/d/github_repository"

  # full_name - (optional) is a type of string
  full_name = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "full_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "github_repository" "this" {
  full_name = var.full_name
  name      = var.name
}
```

[top](#index)

### Outputs

```terraform
output "allow_merge_commit" {
  description = "returns a bool"
  value       = data.github_repository.this.allow_merge_commit
}

output "allow_rebase_merge" {
  description = "returns a bool"
  value       = data.github_repository.this.allow_rebase_merge
}

output "allow_squash_merge" {
  description = "returns a bool"
  value       = data.github_repository.this.allow_squash_merge
}

output "archived" {
  description = "returns a bool"
  value       = data.github_repository.this.archived
}

output "default_branch" {
  description = "returns a string"
  value       = data.github_repository.this.default_branch
}

output "description" {
  description = "returns a string"
  value       = data.github_repository.this.description
}

output "git_clone_url" {
  description = "returns a string"
  value       = data.github_repository.this.git_clone_url
}

output "has_downloads" {
  description = "returns a bool"
  value       = data.github_repository.this.has_downloads
}

output "has_issues" {
  description = "returns a bool"
  value       = data.github_repository.this.has_issues
}

output "has_projects" {
  description = "returns a bool"
  value       = data.github_repository.this.has_projects
}

output "has_wiki" {
  description = "returns a bool"
  value       = data.github_repository.this.has_wiki
}

output "homepage_url" {
  description = "returns a string"
  value       = data.github_repository.this.homepage_url
}

output "html_url" {
  description = "returns a string"
  value       = data.github_repository.this.html_url
}

output "http_clone_url" {
  description = "returns a string"
  value       = data.github_repository.this.http_clone_url
}

output "id" {
  description = "returns a string"
  value       = data.github_repository.this.id
}

output "node_id" {
  description = "returns a string"
  value       = data.github_repository.this.node_id
}

output "pages" {
  description = "returns a list of object"
  value       = data.github_repository.this.pages
}

output "private" {
  description = "returns a bool"
  value       = data.github_repository.this.private
}

output "repo_id" {
  description = "returns a number"
  value       = data.github_repository.this.repo_id
}

output "ssh_clone_url" {
  description = "returns a string"
  value       = data.github_repository.this.ssh_clone_url
}

output "svn_url" {
  description = "returns a string"
  value       = data.github_repository.this.svn_url
}

output "topics" {
  description = "returns a list of string"
  value       = data.github_repository.this.topics
}

output "visibility" {
  description = "returns a string"
  value       = data.github_repository.this.visibility
}

output "this" {
  value = github_repository.this
}
```

[top](#index)