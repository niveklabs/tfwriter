# github_user_gpg_key

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
module "github_user_gpg_key" {
  source = "./modules/github/r/github_user_gpg_key"

  # armored_public_key - (required) is a type of string
  armored_public_key = null
}
```

[top](#index)

### Variables

```terraform
variable "armored_public_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_user_gpg_key" "this" {
  armored_public_key = var.armored_public_key
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_user_gpg_key.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_user_gpg_key.this.id
}

output "key_id" {
  description = "returns a string"
  value       = github_user_gpg_key.this.key_id
}

output "this" {
  value = github_user_gpg_key.this
}
```

[top](#index)