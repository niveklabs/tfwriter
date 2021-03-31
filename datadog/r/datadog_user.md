# datadog_user

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_user" {
  source = "./modules/datadog/r/datadog_user"

  # access_role - (optional) is a type of string
  access_role = null
  # disabled - (optional) is a type of bool
  disabled = null
  # email - (required) is a type of string
  email = null
  # handle - (optional) is a type of string
  handle = null
  # is_admin - (optional) is a type of bool
  is_admin = null
  # name - (optional) is a type of string
  name = null
  # role - (optional) is a type of string
  role = null
  # roles - (optional) is a type of set of string
  roles = []
  # send_user_invitation - (optional) is a type of bool
  send_user_invitation = null
}
```

[top](#index)

### Variables

```terraform
variable "access_role" {
  description = "(optional) - Role description for user. Can be `st` (standard user), `adm` (admin user) or `ro` (read-only user). Default is `st`. `access_role` is ignored for new users created with this resource. New users have to use the `roles` attribute. **Deprecated.** This parameter is replaced by `roles` and will be removed from the next Major version."
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional) - Whether the user is disabled."
  type        = bool
  default     = null
}

variable "email" {
  description = "(required) - Email address for user."
  type        = string
}

variable "handle" {
  description = "(optional) - The user handle, must be a valid email. **Deprecated.** This parameter is deprecated and will be removed from the next Major version."
  type        = string
  default     = null
}

variable "is_admin" {
  description = "(optional) - Whether the user is an administrator. Warning: the corresponding query parameter is ignored by the Datadog API, thus the argument would always trigger an execution plan. **Deprecated.** This parameter is replaced by `roles` and will be removed from the next Major version."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Name for user."
  type        = string
  default     = null
}

variable "role" {
  description = "(optional) - Role description for user. Warning: the corresponding query parameter is ignored by the Datadog API, thus the argument would always trigger an execution plan. **Deprecated.** This parameter was removed from the API and has no effect."
  type        = string
  default     = null
}

variable "roles" {
  description = "(optional) - A list a role IDs to assign to the user."
  type        = set(string)
  default     = null
}

variable "send_user_invitation" {
  description = "(optional) - Whether an invitation email should be sent when the user is created."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_user" "this" {
  access_role          = var.access_role
  disabled             = var.disabled
  email                = var.email
  handle               = var.handle
  is_admin             = var.is_admin
  name                 = var.name
  role                 = var.role
  roles                = var.roles
  send_user_invitation = var.send_user_invitation
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_user.this.id
}

output "is_admin" {
  description = "returns a bool"
  value       = datadog_user.this.is_admin
}

output "user_invitation_id" {
  description = "returns a string"
  value       = datadog_user.this.user_invitation_id
}

output "verified" {
  description = "returns a bool"
  value       = datadog_user.this.verified
}

output "this" {
  value = datadog_user.this
}
```

[top](#index)