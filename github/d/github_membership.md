# github_membership

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
module "github_membership" {
  source = "./modules/github/d/github_membership"

  # organization - (optional) is a type of string
  organization = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "organization" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "github_membership" "this" {
  # organization - (optional) is a type of string
  organization = var.organization
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = data.github_membership.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.github_membership.this.id
}

output "role" {
  description = "returns a string"
  value       = data.github_membership.this.role
}

output "this" {
  value = github_membership.this
}
```

[top](#index)