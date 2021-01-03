# mongodbatlas_project

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
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_project" {
  source = "./modules/mongodbatlas/d/mongodbatlas_project"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
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

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_project" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "cluster_count" {
  description = "returns a number"
  value       = data.mongodbatlas_project.this.cluster_count
}

output "created" {
  description = "returns a string"
  value       = data.mongodbatlas_project.this.created
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_project.this.id
}

output "org_id" {
  description = "returns a string"
  value       = data.mongodbatlas_project.this.org_id
}

output "teams" {
  description = "returns a list of object"
  value       = data.mongodbatlas_project.this.teams
}

output "this" {
  value = mongodbatlas_project.this
}
```

[top](#index)