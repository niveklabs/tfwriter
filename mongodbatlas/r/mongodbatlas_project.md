# mongodbatlas_project

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
module "mongodbatlas_project" {
  source = "./modules/mongodbatlas/r/mongodbatlas_project"

  # name - (required) is a type of string
  name = null
  # org_id - (required) is a type of string
  org_id = null

  teams = [{
    role_names = []
    team_id    = null
  }]
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

variable "teams" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      role_names = set(string)
      team_id    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_project" "this" {
  name   = var.name
  org_id = var.org_id

  dynamic "teams" {
    for_each = var.teams
    content {
      role_names = teams.value["role_names"]
      team_id    = teams.value["team_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_count" {
  description = "returns a number"
  value       = mongodbatlas_project.this.cluster_count
}

output "created" {
  description = "returns a string"
  value       = mongodbatlas_project.this.created
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_project.this.id
}

output "this" {
  value = mongodbatlas_project.this
}
```

[top](#index)