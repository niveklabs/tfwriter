# gitlab_user

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_user" {
  source = "./modules/gitlab/r/gitlab_user"

  # can_create_group - (optional) is a type of bool
  can_create_group = null
  # email - (required) is a type of string
  email = null
  # is_admin - (optional) is a type of bool
  is_admin = null
  # is_external - (optional) is a type of bool
  is_external = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # projects_limit - (optional) is a type of number
  projects_limit = null
  # reset_password - (optional) is a type of bool
  reset_password = null
  # skip_confirmation - (optional) is a type of bool
  skip_confirmation = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "can_create_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "is_admin" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_external" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "projects_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_password" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "skip_confirmation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_user" "this" {
  can_create_group  = var.can_create_group
  email             = var.email
  is_admin          = var.is_admin
  is_external       = var.is_external
  name              = var.name
  password          = var.password
  projects_limit    = var.projects_limit
  reset_password    = var.reset_password
  skip_confirmation = var.skip_confirmation
  username          = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_user.this.id
}

output "this" {
  value = gitlab_user.this
}
```

[top](#index)