# github_organization_block

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
module "github_organization_block" {
  source = "./modules/github/r/github_organization_block"

  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```hcl
variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "github_organization_block" "this" {
  username = var.username
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = github_organization_block.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_organization_block.this.id
}

output "this" {
  value = github_organization_block.this
}
```

[top](#index)