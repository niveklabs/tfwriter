# github_organization_project

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "github_organization_project" {
  source = "./modules/github/r/github_organization_project"

  # body - (optional) is a type of string
  body = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_organization_project" "this" {
  body = var.body
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_organization_project.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_organization_project.this.id
}

output "url" {
  description = "returns a string"
  value       = github_organization_project.this.url
}

output "this" {
  value = github_organization_project.this
}
```

[top](#index)