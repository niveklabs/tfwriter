# mongodbatlas_team

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_team" {
  source = "./modules/mongodbatlas/r/mongodbatlas_team"

  # name - (required) is a type of string
  name = null
  # org_id - (required) is a type of string
  org_id = null
  # usernames - (required) is a type of set of string
  usernames = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "org_id" {
  description = "(required)"
  type        = string
}

variable "usernames" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_team" "this" {
  name      = var.name
  org_id    = var.org_id
  usernames = var.usernames
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mongodbatlas_team.this.id
}

output "team_id" {
  description = "returns a string"
  value       = mongodbatlas_team.this.team_id
}

output "this" {
  value = mongodbatlas_team.this
}
```

[top](#index)