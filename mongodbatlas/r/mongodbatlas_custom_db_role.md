# mongodbatlas_custom_db_role

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
module "mongodbatlas_custom_db_role" {
  source = "./modules/mongodbatlas/r/mongodbatlas_custom_db_role"

  # project_id - (required) is a type of string
  project_id = null
  # role_name - (required) is a type of string
  role_name = null

  actions = [{
    action = null
    resources = [{
      cluster         = null
      collection_name = null
      database_name   = null
    }]
  }]

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

variable "actions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      resources = set(object(
        {
          cluster         = bool
          collection_name = string
          database_name   = string
        }
      ))
    }
  ))
  default = []
}

variable "inherited_roles" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
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

### Resource

```terraform
resource "mongodbatlas_custom_db_role" "this" {
  # project_id - (required) is a type of string
  project_id = var.project_id
  # role_name - (required) is a type of string
  role_name = var.role_name

  dynamic "actions" {
    for_each = var.actions
    content {
      # action - (required) is a type of string
      action = actions.value["action"]

      dynamic "resources" {
        for_each = actions.value.resources
        content {
          # cluster - (optional) is a type of bool
          cluster = resources.value["cluster"]
          # collection_name - (optional) is a type of string
          collection_name = resources.value["collection_name"]
          # database_name - (optional) is a type of string
          database_name = resources.value["database_name"]
        }
      }

    }
  }

  dynamic "inherited_roles" {
    for_each = var.inherited_roles
    content {
      # database_name - (required) is a type of string
      database_name = inherited_roles.value["database_name"]
      # role_name - (required) is a type of string
      role_name = inherited_roles.value["role_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mongodbatlas_custom_db_role.this.id
}

output "this" {
  value = mongodbatlas_custom_db_role.this
}
```

[top](#index)