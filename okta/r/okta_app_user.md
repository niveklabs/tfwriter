# okta_app_user

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app_user" {
  source = "./modules/okta/r/okta_app_user"

  # app_id - (required) is a type of string
  app_id = null
  # password - (optional) is a type of string
  password = null
  # profile - (optional) is a type of string
  profile = null
  # retain_assignment - (optional) is a type of bool
  retain_assignment = null
  # user_id - (required) is a type of string
  user_id = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required) - App to associate user with"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retain_assignment" {
  description = "(optional) - Retain the user assignment on destroy. If set to true, the resource will be removed from state but not from the Okta app."
  type        = bool
  default     = null
}

variable "user_id" {
  description = "(required) - User associated with the application"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_app_user" "this" {
  app_id            = var.app_id
  password          = var.password
  profile           = var.profile
  retain_assignment = var.retain_assignment
  user_id           = var.user_id
  username          = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_app_user.this.id
}

output "this" {
  value = okta_app_user.this
}
```

[top](#index)