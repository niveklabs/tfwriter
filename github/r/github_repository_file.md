# github_repository_file

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "github_repository_file" {
  source = "./modules/github/r/github_repository_file"

  # branch - (optional) is a type of string
  branch = null
  # commit_author - (optional) is a type of string
  commit_author = null
  # commit_email - (optional) is a type of string
  commit_email = null
  # commit_message - (optional) is a type of string
  commit_message = null
  # content - (required) is a type of string
  content = null
  # file - (required) is a type of string
  file = null
  # overwrite_on_create - (optional) is a type of bool
  overwrite_on_create = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "branch" {
  description = "(optional) - The branch name, defaults to \"main\""
  type        = string
  default     = null
}

variable "commit_author" {
  description = "(optional) - The commit author name, defaults to the authenticated user's name"
  type        = string
  default     = null
}

variable "commit_email" {
  description = "(optional) - The commit author email address, defaults to the authenticated user's email address"
  type        = string
  default     = null
}

variable "commit_message" {
  description = "(optional) - The commit message when creating or updating the file"
  type        = string
  default     = null
}

variable "content" {
  description = "(required) - The file's content"
  type        = string
}

variable "file" {
  description = "(required) - The file path to manage"
  type        = string
}

variable "overwrite_on_create" {
  description = "(optional) - Enable overwriting existing files, defaults to \"false\""
  type        = bool
  default     = null
}

variable "repository" {
  description = "(required) - The repository name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_repository_file" "this" {
  # branch - (optional) is a type of string
  branch = var.branch
  # commit_author - (optional) is a type of string
  commit_author = var.commit_author
  # commit_email - (optional) is a type of string
  commit_email = var.commit_email
  # commit_message - (optional) is a type of string
  commit_message = var.commit_message
  # content - (required) is a type of string
  content = var.content
  # file - (required) is a type of string
  file = var.file
  # overwrite_on_create - (optional) is a type of bool
  overwrite_on_create = var.overwrite_on_create
  # repository - (required) is a type of string
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "commit_author" {
  description = "returns a string"
  value       = github_repository_file.this.commit_author
}

output "commit_email" {
  description = "returns a string"
  value       = github_repository_file.this.commit_email
}

output "commit_message" {
  description = "returns a string"
  value       = github_repository_file.this.commit_message
}

output "commit_sha" {
  description = "returns a string"
  value       = github_repository_file.this.commit_sha
}

output "id" {
  description = "returns a string"
  value       = github_repository_file.this.id
}

output "sha" {
  description = "returns a string"
  value       = github_repository_file.this.sha
}

output "this" {
  value = github_repository_file.this
}
```

[top](#index)