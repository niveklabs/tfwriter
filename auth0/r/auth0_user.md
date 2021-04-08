# auth0_user

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_user" {
  source = "./modules/auth0/r/auth0_user"

  # app_metadata - (optional) is a type of string
  app_metadata = null
  # blocked - (optional) is a type of bool
  blocked = null
  # connection_name - (required) is a type of string
  connection_name = null
  # email - (optional) is a type of string
  email = null
  # email_verified - (optional) is a type of bool
  email_verified = null
  # family_name - (optional) is a type of string
  family_name = null
  # given_name - (optional) is a type of string
  given_name = null
  # name - (optional) is a type of string
  name = null
  # nickname - (optional) is a type of string
  nickname = null
  # password - (optional) is a type of string
  password = null
  # phone_number - (optional) is a type of string
  phone_number = null
  # phone_verified - (optional) is a type of bool
  phone_verified = null
  # picture - (optional) is a type of string
  picture = null
  # roles - (optional) is a type of set of string
  roles = []
  # user_id - (optional) is a type of string
  user_id = null
  # user_metadata - (optional) is a type of string
  user_metadata = null
  # username - (optional) is a type of string
  username = null
  # verify_email - (optional) is a type of bool
  verify_email = null
}
```

[top](#index)

### Variables

```terraform
variable "app_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "blocked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "connection_name" {
  description = "(required)"
  type        = string
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_verified" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "family_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "given_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nickname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "phone_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "phone_verified" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "picture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "verify_email" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "auth0_user" "this" {
  # app_metadata - (optional) is a type of string
  app_metadata = var.app_metadata
  # blocked - (optional) is a type of bool
  blocked = var.blocked
  # connection_name - (required) is a type of string
  connection_name = var.connection_name
  # email - (optional) is a type of string
  email = var.email
  # email_verified - (optional) is a type of bool
  email_verified = var.email_verified
  # family_name - (optional) is a type of string
  family_name = var.family_name
  # given_name - (optional) is a type of string
  given_name = var.given_name
  # name - (optional) is a type of string
  name = var.name
  # nickname - (optional) is a type of string
  nickname = var.nickname
  # password - (optional) is a type of string
  password = var.password
  # phone_number - (optional) is a type of string
  phone_number = var.phone_number
  # phone_verified - (optional) is a type of bool
  phone_verified = var.phone_verified
  # picture - (optional) is a type of string
  picture = var.picture
  # roles - (optional) is a type of set of string
  roles = var.roles
  # user_id - (optional) is a type of string
  user_id = var.user_id
  # user_metadata - (optional) is a type of string
  user_metadata = var.user_metadata
  # username - (optional) is a type of string
  username = var.username
  # verify_email - (optional) is a type of bool
  verify_email = var.verify_email
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_user.this.id
}

output "name" {
  description = "returns a string"
  value       = auth0_user.this.name
}

output "nickname" {
  description = "returns a string"
  value       = auth0_user.this.nickname
}

output "picture" {
  description = "returns a string"
  value       = auth0_user.this.picture
}

output "user_id" {
  description = "returns a string"
  value       = auth0_user.this.user_id
}

output "this" {
  value = auth0_user.this
}
```

[top](#index)