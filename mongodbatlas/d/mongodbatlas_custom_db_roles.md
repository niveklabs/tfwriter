# mongodbatlas_custom_db_roles

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
module "mongodbatlas_custom_db_roles" {
  source = "./modules/mongodbatlas/d/mongodbatlas_custom_db_roles"

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
data "mongodbatlas_custom_db_roles" "this" {
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_custom_db_roles.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.mongodbatlas_custom_db_roles.this.results
}

output "this" {
  value = mongodbatlas_custom_db_roles.this
}
```

[top](#index)