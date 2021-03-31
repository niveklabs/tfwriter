# mongodbatlas_x509_authentication_database_user

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
module "mongodbatlas_x509_authentication_database_user" {
  source = "./modules/mongodbatlas/r/mongodbatlas_x509_authentication_database_user"

  # customer_x509_cas - (optional) is a type of string
  customer_x509_cas = null
  # months_until_expiration - (optional) is a type of number
  months_until_expiration = null
  # project_id - (required) is a type of string
  project_id = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "customer_x509_cas" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "months_until_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

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

### Resource

```terraform
resource "mongodbatlas_x509_authentication_database_user" "this" {
  customer_x509_cas       = var.customer_x509_cas
  months_until_expiration = var.months_until_expiration
  project_id              = var.project_id
  username                = var.username
}
```

[top](#index)

### Outputs

```terraform
output "certificates" {
  description = "returns a list of object"
  value       = mongodbatlas_x509_authentication_database_user.this.certificates
}

output "current_certificate" {
  description = "returns a string"
  value       = mongodbatlas_x509_authentication_database_user.this.current_certificate
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_x509_authentication_database_user.this.id
}

output "this" {
  value = mongodbatlas_x509_authentication_database_user.this
}
```

[top](#index)