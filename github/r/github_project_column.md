# github_project_column

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
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_project_column" {
  source = "./modules/github/r/github_project_column"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_project_column" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "column_id" {
  description = "returns a number"
  value       = github_project_column.this.column_id
}

output "etag" {
  description = "returns a string"
  value       = github_project_column.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_project_column.this.id
}

output "this" {
  value = github_project_column.this
}
```

[top](#index)