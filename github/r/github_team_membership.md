# github_team_membership

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
module "github_team_membership" {
  source = "./modules/github/r/github_team_membership"

  # role - (optional) is a type of string
  role = null
  # team_id - (required) is a type of string
  team_id = null
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

variable "team_id" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_team_membership" "this" {
  role     = var.role
  team_id  = var.team_id
  username = var.username
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_team_membership.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_team_membership.this.id
}

output "this" {
  value = github_team_membership.this
}
```

[top](#index)