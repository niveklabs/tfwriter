# github_user_gpg_key

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
module "github_user_gpg_key" {
  source = "./modules/github/r/github_user_gpg_key"

  # armored_public_key - (required) is a type of string
  armored_public_key = null
}
```

[top](#index)

### Variables

```hcl
variable "armored_public_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_user_gpg_key" "this" {
  armored_public_key = var.armored_public_key
}
```

[top](#index)

### Outputs

```hcl
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