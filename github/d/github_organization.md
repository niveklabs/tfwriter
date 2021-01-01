# github_organization

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
module "github_organization" {
  source = "./modules/github/d/github_organization"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "github_organization" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = data.github_organization.this.description
}

output "id" {
  description = "returns a string"
  value       = data.github_organization.this.id
}

output "login" {
  description = "returns a string"
  value       = data.github_organization.this.login
}

output "node_id" {
  description = "returns a string"
  value       = data.github_organization.this.node_id
}

output "plan" {
  description = "returns a string"
  value       = data.github_organization.this.plan
}

output "this" {
  value = github_organization.this
}
```

[top](#index)