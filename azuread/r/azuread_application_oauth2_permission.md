# azuread_application_oauth2_permission

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
    azuread = ">= 1.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_application_oauth2_permission" {
  source = "./modules/azuread/r/azuread_application_oauth2_permission"

  # admin_consent_description - (required) is a type of string
  admin_consent_description = null
  # admin_consent_display_name - (required) is a type of string
  admin_consent_display_name = null
  # application_object_id - (required) is a type of string
  application_object_id = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # permission_id - (optional) is a type of string
  permission_id = null
  # type - (required) is a type of string
  type = null
  # user_consent_description - (required) is a type of string
  user_consent_description = null
  # user_consent_display_name - (required) is a type of string
  user_consent_display_name = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_consent_description" {
  description = "(required)"
  type        = string
}

variable "admin_consent_display_name" {
  description = "(required)"
  type        = string
}

variable "application_object_id" {
  description = "(required)"
  type        = string
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "permission_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "user_consent_description" {
  description = "(required)"
  type        = string
}

variable "user_consent_display_name" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuread_application_oauth2_permission" "this" {
  admin_consent_description  = var.admin_consent_description
  admin_consent_display_name = var.admin_consent_display_name
  application_object_id      = var.application_object_id
  is_enabled                 = var.is_enabled
  permission_id              = var.permission_id
  type                       = var.type
  user_consent_description   = var.user_consent_description
  user_consent_display_name  = var.user_consent_display_name
  value                      = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuread_application_oauth2_permission.this.id
}

output "permission_id" {
  description = "returns a string"
  value       = azuread_application_oauth2_permission.this.permission_id
}

output "this" {
  value = azuread_application_oauth2_permission.this
}
```

[top](#index)