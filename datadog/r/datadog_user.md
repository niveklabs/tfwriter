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
    datadog = ">= 2.18.1"
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
}
```

[top](#index)

### Variables

```terraform
variable "access_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "handle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_admin" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_user" "this" {
  access_role = var.access_role
  disabled    = var.disabled
  email       = var.email
  handle      = var.handle
  is_admin    = var.is_admin
  name        = var.name
  role        = var.role
  roles       = var.roles
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

output "verified" {
  description = "returns a bool"
  value       = datadog_user.this.verified
}

output "this" {
  value = datadog_user.this
}
```

[top](#index)