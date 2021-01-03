# ad_user

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_user" {
  source = "./modules/ad/r/ad_user"

  # cannot_change_password - (optional) is a type of bool
  cannot_change_password = null
  # container - (optional) is a type of string
  container = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # initial_password - (optional) is a type of string
  initial_password = null
  # password_never_expires - (optional) is a type of bool
  password_never_expires = null
  # principal_name - (required) is a type of string
  principal_name = null
  # sam_account_name - (required) is a type of string
  sam_account_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cannot_change_password" {
  description = "(optional) - If set to true, the user will not be allowed to change their password."
  type        = bool
  default     = null
}

variable "container" {
  description = "(optional) - A DN of the container object that will be holding the user."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - The Display Name of an Active Directory user."
  type        = string
}

variable "enabled" {
  description = "(optional) - If set to false, the user will be disabled."
  type        = bool
  default     = null
}

variable "initial_password" {
  description = "(optional) - The user's initial password. This will be set on creation but will *not* be enforced in subsequent plans."
  type        = string
  default     = null
}

variable "password_never_expires" {
  description = "(optional) - If set to true, the password for this user will not expire."
  type        = bool
  default     = null
}

variable "principal_name" {
  description = "(required) - The Principal Name of an Active Directory user."
  type        = string
}

variable "sam_account_name" {
  description = "(required) - The pre-win2k user logon name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ad_user" "this" {
  cannot_change_password = var.cannot_change_password
  container              = var.container
  display_name           = var.display_name
  enabled                = var.enabled
  initial_password       = var.initial_password
  password_never_expires = var.password_never_expires
  principal_name         = var.principal_name
  sam_account_name       = var.sam_account_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ad_user.this.id
}

output "this" {
  value = ad_user.this
}
```

[top](#index)