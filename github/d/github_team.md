# github_team

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
module "github_team" {
  source = "./modules/github/d/github_team"

  # slug - (required) is a type of string
  slug = null
}
```

[top](#index)

### Variables

```hcl
variable "slug" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "github_team" "this" {
  slug = var.slug
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = data.github_team.this.description
}

output "id" {
  description = "returns a string"
  value       = data.github_team.this.id
}

output "members" {
  description = "returns a list of string"
  value       = data.github_team.this.members
}

output "name" {
  description = "returns a string"
  value       = data.github_team.this.name
}

output "node_id" {
  description = "returns a string"
  value       = data.github_team.this.node_id
}

output "permission" {
  description = "returns a string"
  value       = data.github_team.this.permission
}

output "privacy" {
  description = "returns a string"
  value       = data.github_team.this.privacy
}

output "this" {
  value = github_team.this
}
```

[top](#index)