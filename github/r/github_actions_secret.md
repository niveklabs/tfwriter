# github_actions_secret

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
module "github_actions_secret" {
  source = "./modules/github/r/github_actions_secret"

  # plaintext_value - (required) is a type of string
  plaintext_value = null
  # repository - (required) is a type of string
  repository = null
  # secret_name - (required) is a type of string
  secret_name = null
}
```

[top](#index)

### Variables

```hcl
variable "plaintext_value" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "secret_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_actions_secret" "this" {
  plaintext_value = var.plaintext_value
  repository      = var.repository
  secret_name     = var.secret_name
}
```

[top](#index)

### Outputs

```hcl
output "created_at" {
  description = "returns a string"
  value       = github_actions_secret.this.created_at
}

output "id" {
  description = "returns a string"
  value       = github_actions_secret.this.id
}

output "updated_at" {
  description = "returns a string"
  value       = github_actions_secret.this.updated_at
}

output "this" {
  value = github_actions_secret.this
}
```

[top](#index)