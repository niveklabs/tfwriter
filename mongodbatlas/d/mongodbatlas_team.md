# mongodbatlas_team

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "mongodbatlas_team" {
  source = "./modules/mongodbatlas/d/mongodbatlas_team"

  # name - (optional) is a type of string
  name = null
  # org_id - (required) is a type of string
  org_id = null
  # team_id - (optional) is a type of string
  team_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "org_id" {
  description = "(required)"
  type        = string
}

variable "team_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_team" "this" {
  name    = var.name
  org_id  = var.org_id
  team_id = var.team_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_team.this.id
}

output "name" {
  description = "returns a string"
  value       = data.mongodbatlas_team.this.name
}

output "team_id" {
  description = "returns a string"
  value       = data.mongodbatlas_team.this.team_id
}

output "usernames" {
  description = "returns a set of string"
  value       = data.mongodbatlas_team.this.usernames
}

output "this" {
  value = mongodbatlas_team.this
}
```

[top](#index)