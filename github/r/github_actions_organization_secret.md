# github_actions_organization_secret

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
module "github_actions_organization_secret" {
  source = "./modules/github/r/github_actions_organization_secret"

  # plaintext_value - (required) is a type of string
  plaintext_value = null
  # secret_name - (required) is a type of string
  secret_name = null
  # selected_repository_ids - (optional) is a type of set of number
  selected_repository_ids = []
  # visibility - (required) is a type of string
  visibility = null
}
```

[top](#index)

### Variables

```terraform
variable "plaintext_value" {
  description = "(required)"
  type        = string
}

variable "secret_name" {
  description = "(required)"
  type        = string
}

variable "selected_repository_ids" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "visibility" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_actions_organization_secret" "this" {
  plaintext_value         = var.plaintext_value
  secret_name             = var.secret_name
  selected_repository_ids = var.selected_repository_ids
  visibility              = var.visibility
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = github_actions_organization_secret.this.created_at
}

output "id" {
  description = "returns a string"
  value       = github_actions_organization_secret.this.id
}

output "updated_at" {
  description = "returns a string"
  value       = github_actions_organization_secret.this.updated_at
}

output "this" {
  value = github_actions_organization_secret.this
}
```

[top](#index)