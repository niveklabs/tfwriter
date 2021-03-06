# github_repositories

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
module "github_repositories" {
  source = "./modules/github/d/github_repositories"

  # query - (required) is a type of string
  query = null
  # sort - (optional) is a type of string
  sort = null
}
```

[top](#index)

### Variables

```terraform
variable "query" {
  description = "(required)"
  type        = string
}

variable "sort" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "github_repositories" "this" {
  # query - (required) is a type of string
  query = var.query
  # sort - (optional) is a type of string
  sort = var.sort
}
```

[top](#index)

### Outputs

```terraform
output "full_names" {
  description = "returns a list of string"
  value       = data.github_repositories.this.full_names
}

output "id" {
  description = "returns a string"
  value       = data.github_repositories.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.github_repositories.this.names
}

output "this" {
  value = github_repositories.this
}
```

[top](#index)