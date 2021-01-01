# github_repository

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "github_repository" {
  source = "./modules/github/r/github_repository"

  # allow_merge_commit - (optional) is a type of bool
  allow_merge_commit = null
  # allow_rebase_merge - (optional) is a type of bool
  allow_rebase_merge = null
  # allow_squash_merge - (optional) is a type of bool
  allow_squash_merge = null
  # archive_on_destroy - (optional) is a type of bool
  archive_on_destroy = null
  # archived - (optional) is a type of bool
  archived = null
  # auto_init - (optional) is a type of bool
  auto_init = null
  # default_branch - (optional) is a type of string
  default_branch = null
  # delete_branch_on_merge - (optional) is a type of bool
  delete_branch_on_merge = null
  # description - (optional) is a type of string
  description = null
  # gitignore_template - (optional) is a type of string
  gitignore_template = null
  # has_downloads - (optional) is a type of bool
  has_downloads = null
  # has_issues - (optional) is a type of bool
  has_issues = null
  # has_projects - (optional) is a type of bool
  has_projects = null
  # has_wiki - (optional) is a type of bool
  has_wiki = null
  # homepage_url - (optional) is a type of string
  homepage_url = null
  # is_template - (optional) is a type of bool
  is_template = null
  # license_template - (optional) is a type of string
  license_template = null
  # name - (required) is a type of string
  name = null
  # private - (optional) is a type of bool
  private = null
  # topics - (optional) is a type of set of string
  topics = []
  # visibility - (optional) is a type of string
  visibility = null
  # vulnerability_alerts - (optional) is a type of bool
  vulnerability_alerts = null

  template = [{
    owner      = null
    repository = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "allow_merge_commit" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_rebase_merge" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_squash_merge" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "archive_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "archived" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_init" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "default_branch" {
  description = "(optional) - Can only be set after initial repository creation, and only if the target branch exists"
  type        = string
  default     = null
}

variable "delete_branch_on_merge" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gitignore_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "has_downloads" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "has_issues" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "has_projects" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "has_wiki" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "homepage_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_template" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "private" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "topics" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vulnerability_alerts" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "template" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      owner      = string
      repository = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "github_repository" "this" {
  allow_merge_commit     = var.allow_merge_commit
  allow_rebase_merge     = var.allow_rebase_merge
  allow_squash_merge     = var.allow_squash_merge
  archive_on_destroy     = var.archive_on_destroy
  archived               = var.archived
  auto_init              = var.auto_init
  default_branch         = var.default_branch
  delete_branch_on_merge = var.delete_branch_on_merge
  description            = var.description
  gitignore_template     = var.gitignore_template
  has_downloads          = var.has_downloads
  has_issues             = var.has_issues
  has_projects           = var.has_projects
  has_wiki               = var.has_wiki
  homepage_url           = var.homepage_url
  is_template            = var.is_template
  license_template       = var.license_template
  name                   = var.name
  private                = var.private
  topics                 = var.topics
  visibility             = var.visibility
  vulnerability_alerts   = var.vulnerability_alerts

  dynamic "template" {
    for_each = var.template
    content {
      owner      = template.value["owner"]
      repository = template.value["repository"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "default_branch" {
  description = "returns a string"
  value       = github_repository.this.default_branch
}

output "etag" {
  description = "returns a string"
  value       = github_repository.this.etag
}

output "full_name" {
  description = "returns a string"
  value       = github_repository.this.full_name
}

output "git_clone_url" {
  description = "returns a string"
  value       = github_repository.this.git_clone_url
}

output "html_url" {
  description = "returns a string"
  value       = github_repository.this.html_url
}

output "http_clone_url" {
  description = "returns a string"
  value       = github_repository.this.http_clone_url
}

output "id" {
  description = "returns a string"
  value       = github_repository.this.id
}

output "node_id" {
  description = "returns a string"
  value       = github_repository.this.node_id
}

output "private" {
  description = "returns a bool"
  value       = github_repository.this.private
}

output "repo_id" {
  description = "returns a number"
  value       = github_repository.this.repo_id
}

output "ssh_clone_url" {
  description = "returns a string"
  value       = github_repository.this.ssh_clone_url
}

output "svn_url" {
  description = "returns a string"
  value       = github_repository.this.svn_url
}

output "visibility" {
  description = "returns a string"
  value       = github_repository.this.visibility
}

output "this" {
  value = github_repository.this
}
```

[top](#index)