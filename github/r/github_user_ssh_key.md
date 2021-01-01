# github_user_ssh_key

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
module "github_user_ssh_key" {
  source = "./modules/github/r/github_user_ssh_key"

  # key - (required) is a type of string
  key = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```hcl
variable "key" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_user_ssh_key" "this" {
  key   = var.key
  title = var.title
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_user_ssh_key.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_user_ssh_key.this.id
}

output "url" {
  description = "returns a string"
  value       = github_user_ssh_key.this.url
}

output "this" {
  value = github_user_ssh_key.this
}
```

[top](#index)