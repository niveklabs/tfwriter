# mongodbatlas_x509_authentication_database_user

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
module "mongodbatlas_x509_authentication_database_user" {
  source = "./modules/mongodbatlas/d/mongodbatlas_x509_authentication_database_user"

  # project_id - (required) is a type of string
  project_id = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_x509_authentication_database_user" "this" {
  project_id = var.project_id
  username   = var.username
}
```

[top](#index)

### Outputs

```terraform
output "certificates" {
  description = "returns a list of object"
  value       = data.mongodbatlas_x509_authentication_database_user.this.certificates
}

output "customer_x509_cas" {
  description = "returns a string"
  value       = data.mongodbatlas_x509_authentication_database_user.this.customer_x509_cas
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_x509_authentication_database_user.this.id
}

output "this" {
  value = mongodbatlas_x509_authentication_database_user.this
}
```

[top](#index)