# github_project_card

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
module "github_project_card" {
  source = "./modules/github/r/github_project_card"

  # column_id - (required) is a type of string
  column_id = null
  # note - (required) is a type of string
  note = null
}
```

[top](#index)

### Variables

```terraform
variable "column_id" {
  description = "(required)"
  type        = string
}

variable "note" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_project_card" "this" {
  column_id = var.column_id
  note      = var.note
}
```

[top](#index)

### Outputs

```terraform
output "card_id" {
  description = "returns a number"
  value       = github_project_card.this.card_id
}

output "etag" {
  description = "returns a string"
  value       = github_project_card.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_project_card.this.id
}

output "this" {
  value = github_project_card.this
}
```

[top](#index)