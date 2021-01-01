# github_membership

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
module "github_membership" {
  source = "./modules/github/r/github_membership"

  # role - (optional) is a type of string
  role = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```hcl
variable "role" {
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

### Resource

```hcl
resource "github_membership" "this" {
  role     = var.role
  username = var.username
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_membership.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_membership.this.id
}

output "this" {
  value = github_membership.this
}
```

[top](#index)