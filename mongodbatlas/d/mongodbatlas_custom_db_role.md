# mongodbatlas_custom_db_role

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
module "mongodbatlas_custom_db_role" {
  source = "./modules/mongodbatlas/d/mongodbatlas_custom_db_role"

  # project_id - (required) is a type of string
  project_id = null
  # role_name - (required) is a type of string
  role_name = null

  inherited_roles = [{
    database_name = null
    role_name     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}

variable "role_name" {
  description = "(required)"
  type        = string
}

variable "inherited_roles" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database_name = string
      role_name     = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_custom_db_role" "this" {
  project_id = var.project_id
  role_name  = var.role_name

  dynamic "inherited_roles" {
    for_each = var.inherited_roles
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "actions" {
  description = "returns a list of object"
  value       = data.mongodbatlas_custom_db_role.this.actions
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_custom_db_role.this.id
}

output "this" {
  value = mongodbatlas_custom_db_role.this
}
```

[top](#index)