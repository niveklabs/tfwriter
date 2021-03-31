# mongodbatlas_database_user

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
module "mongodbatlas_database_user" {
  source = "./modules/mongodbatlas/r/mongodbatlas_database_user"

  # auth_database_name - (optional) is a type of string
  auth_database_name = null
  # aws_iam_type - (optional) is a type of string
  aws_iam_type = null
  # database_name - (optional) is a type of string
  database_name = null
  # password - (optional) is a type of string
  password = null
  # project_id - (required) is a type of string
  project_id = null
  # username - (required) is a type of string
  username = null
  # x509_type - (optional) is a type of string
  x509_type = null

  labels = [{
    key   = null
    value = null
  }]

  roles = [{
    collection_name = null
    database_name   = null
    role_name       = null
  }]

  scopes = [{
    name = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_iam_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "x509_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "roles" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      collection_name = string
      database_name   = string
      role_name       = string
    }
  ))
}

variable "scopes" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_database_user" "this" {
  auth_database_name = var.auth_database_name
  aws_iam_type       = var.aws_iam_type
  database_name      = var.database_name
  password           = var.password
  project_id         = var.project_id
  username           = var.username
  x509_type          = var.x509_type

  dynamic "labels" {
    for_each = var.labels
    content {
      key   = labels.value["key"]
      value = labels.value["value"]
    }
  }

  dynamic "roles" {
    for_each = var.roles
    content {
      collection_name = roles.value["collection_name"]
      database_name   = roles.value["database_name"]
      role_name       = roles.value["role_name"]
    }
  }

  dynamic "scopes" {
    for_each = var.scopes
    content {
      name = scopes.value["name"]
      type = scopes.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mongodbatlas_database_user.this.id
}

output "this" {
  value = mongodbatlas_database_user.this
}
```

[top](#index)