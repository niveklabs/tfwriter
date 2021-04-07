# ovh_me_identity_user

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_identity_user" {
  source = "./modules/ovh/r/ovh_me_identity_user"

  # description - (optional) is a type of string
  description = null
  # email - (required) is a type of string
  email = null
  # group - (optional) is a type of string
  group = null
  # login - (required) is a type of string
  login = null
  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - User description"
  type        = string
  default     = null
}

variable "email" {
  description = "(required) - User's email"
  type        = string
}

variable "group" {
  description = "(optional) - User's group"
  type        = string
  default     = null
}

variable "login" {
  description = "(required) - User's login suffix"
  type        = string
}

variable "password" {
  description = "(required) - User's password"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_identity_user" "this" {
  # description - (optional) is a type of string
  description = var.description
  # email - (required) is a type of string
  email = var.email
  # group - (optional) is a type of string
  group = var.group
  # login - (required) is a type of string
  login = var.login
  # password - (required) is a type of string
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "creation" {
  description = "returns a string"
  value       = ovh_me_identity_user.this.creation
}

output "id" {
  description = "returns a string"
  value       = ovh_me_identity_user.this.id
}

output "last_update" {
  description = "returns a string"
  value       = ovh_me_identity_user.this.last_update
}

output "password_last_update" {
  description = "returns a string"
  value       = ovh_me_identity_user.this.password_last_update
}

output "status" {
  description = "returns a string"
  value       = ovh_me_identity_user.this.status
}

output "this" {
  value = ovh_me_identity_user.this
}
```

[top](#index)