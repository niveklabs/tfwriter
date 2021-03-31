# azuread_application_app_role

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_application_app_role" {
  source = "./modules/azuread/r/azuread_application_app_role"

  # allowed_member_types - (required) is a type of set of string
  allowed_member_types = []
  # application_object_id - (required) is a type of string
  application_object_id = null
  # description - (required) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # role_id - (optional) is a type of string
  role_id = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_member_types" {
  description = "(required)"
  type        = set(string)
}

variable "application_object_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "role_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuread_application_app_role" "this" {
  allowed_member_types  = var.allowed_member_types
  application_object_id = var.application_object_id
  description           = var.description
  display_name          = var.display_name
  is_enabled            = var.is_enabled
  role_id               = var.role_id
  value                 = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuread_application_app_role.this.id
}

output "role_id" {
  description = "returns a string"
  value       = azuread_application_app_role.this.role_id
}

output "this" {
  value = azuread_application_app_role.this
}
```

[top](#index)