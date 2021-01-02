# github_release

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
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_release" {
  source = "./modules/github/d/github_release"

  # owner - (required) is a type of string
  owner = null
  # release_id - (optional) is a type of number
  release_id = null
  # release_tag - (optional) is a type of string
  release_tag = null
  # repository - (required) is a type of string
  repository = null
  # retrieve_by - (required) is a type of string
  retrieve_by = null
}
```

[top](#index)

### Variables

```terraform
variable "owner" {
  description = "(required)"
  type        = string
}

variable "release_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "release_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "retrieve_by" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "github_release" "this" {
  owner       = var.owner
  release_id  = var.release_id
  release_tag = var.release_tag
  repository  = var.repository
  retrieve_by = var.retrieve_by
}
```

[top](#index)

### Outputs

```terraform
output "asserts_url" {
  description = "returns a string"
  value       = data.github_release.this.asserts_url
}

output "body" {
  description = "returns a string"
  value       = data.github_release.this.body
}

output "created_at" {
  description = "returns a string"
  value       = data.github_release.this.created_at
}

output "draft" {
  description = "returns a bool"
  value       = data.github_release.this.draft
}

output "html_url" {
  description = "returns a string"
  value       = data.github_release.this.html_url
}

output "id" {
  description = "returns a string"
  value       = data.github_release.this.id
}

output "name" {
  description = "returns a string"
  value       = data.github_release.this.name
}

output "prerelease" {
  description = "returns a bool"
  value       = data.github_release.this.prerelease
}

output "published_at" {
  description = "returns a string"
  value       = data.github_release.this.published_at
}

output "tarball_url" {
  description = "returns a string"
  value       = data.github_release.this.tarball_url
}

output "target_commitish" {
  description = "returns a string"
  value       = data.github_release.this.target_commitish
}

output "upload_url" {
  description = "returns a string"
  value       = data.github_release.this.upload_url
}

output "url" {
  description = "returns a string"
  value       = data.github_release.this.url
}

output "zipball_url" {
  description = "returns a string"
  value       = data.github_release.this.zipball_url
}

output "this" {
  value = github_release.this
}
```

[top](#index)