# mongodbatlas_database_user

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
module "mongodbatlas_database_user" {
  source = "./modules/mongodbatlas/d/mongodbatlas_database_user"

  # auth_database_name - (optional) is a type of string
  auth_database_name = null
  # database_name - (optional) is a type of string
  database_name = null
  # project_id - (required) is a type of string
  project_id = null
  # username - (required) is a type of string
  username = null
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

variable "database_name" {
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
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_database_user" "this" {
  # auth_database_name - (optional) is a type of string
  auth_database_name = var.auth_database_name
  # database_name - (optional) is a type of string
  database_name = var.database_name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "aws_iam_type" {
  description = "returns a string"
  value       = data.mongodbatlas_database_user.this.aws_iam_type
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_database_user.this.id
}

output "labels" {
  description = "returns a list of object"
  value       = data.mongodbatlas_database_user.this.labels
}

output "roles" {
  description = "returns a list of object"
  value       = data.mongodbatlas_database_user.this.roles
}

output "scopes" {
  description = "returns a list of object"
  value       = data.mongodbatlas_database_user.this.scopes
}

output "x509_type" {
  description = "returns a string"
  value       = data.mongodbatlas_database_user.this.x509_type
}

output "this" {
  value = mongodbatlas_database_user.this
}
```

[top](#index)