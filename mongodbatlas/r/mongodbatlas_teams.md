# mongodbatlas_teams

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
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_teams" {
  source = "./modules/mongodbatlas/r/mongodbatlas_teams"

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
resource "mongodbatlas_teams" "this" {
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
  value       = mongodbatlas_teams.this.id
}

output "team_id" {
  description = "returns a string"
  value       = mongodbatlas_teams.this.team_id
}

output "this" {
  value = mongodbatlas_teams.this
}
```

[top](#index)