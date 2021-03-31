# github_actions_public_key

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
module "github_actions_public_key" {
  source = "./modules/github/d/github_actions_public_key"

  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "github_actions_public_key" "this" {
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.github_actions_public_key.this.id
}

output "key" {
  description = "returns a string"
  value       = data.github_actions_public_key.this.key
}

output "key_id" {
  description = "returns a string"
  value       = data.github_actions_public_key.this.key_id
}

output "this" {
  value = github_actions_public_key.this
}
```

[top](#index)