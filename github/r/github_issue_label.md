# github_issue_label

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
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_issue_label" {
  source = "./modules/github/r/github_issue_label"

  # color - (required) is a type of string
  color = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_issue_label" "this" {
  color       = var.color
  description = var.description
  name        = var.name
  repository  = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_issue_label.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_issue_label.this.id
}

output "url" {
  description = "returns a string"
  value       = github_issue_label.this.url
}

output "this" {
  value = github_issue_label.this
}
```

[top](#index)