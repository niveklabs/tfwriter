# mongodbatlas_maintenance_window

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
module "mongodbatlas_maintenance_window" {
  source = "./modules/mongodbatlas/d/mongodbatlas_maintenance_window"

  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_maintenance_window" "this" {
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "day_of_week" {
  description = "returns a number"
  value       = data.mongodbatlas_maintenance_window.this.day_of_week
}

output "hour_of_day" {
  description = "returns a number"
  value       = data.mongodbatlas_maintenance_window.this.hour_of_day
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_maintenance_window.this.id
}

output "number_of_deferrals" {
  description = "returns a number"
  value       = data.mongodbatlas_maintenance_window.this.number_of_deferrals
}

output "start_asap" {
  description = "returns a bool"
  value       = data.mongodbatlas_maintenance_window.this.start_asap
}

output "this" {
  value = mongodbatlas_maintenance_window.this
}
```

[top](#index)