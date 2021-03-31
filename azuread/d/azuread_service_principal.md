# azuread_service_principal

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azuread_service_principal" {
  source = "./modules/azuread/d/azuread_service_principal"

  # application_id - (optional) is a type of string
  application_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # object_id - (optional) is a type of string
  object_id = null

  oauth2_permissions = [{
    admin_consent_description  = null
    admin_consent_display_name = null
    id                         = null
    is_enabled                 = null
    type                       = null
    user_consent_description   = null
    user_consent_display_name  = null
    value                      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oauth2_permissions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      admin_consent_description  = string
      admin_consent_display_name = string
      id                         = string
      is_enabled                 = bool
      type                       = string
      user_consent_description   = string
      user_consent_display_name  = string
      value                      = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azuread_service_principal" "this" {
  application_id = var.application_id
  display_name   = var.display_name
  object_id      = var.object_id

  dynamic "oauth2_permissions" {
    for_each = var.oauth2_permissions
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_roles" {
  description = "returns a list of object"
  value       = data.azuread_service_principal.this.app_roles
}

output "application_id" {
  description = "returns a string"
  value       = data.azuread_service_principal.this.application_id
}

output "display_name" {
  description = "returns a string"
  value       = data.azuread_service_principal.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azuread_service_principal.this.id
}

output "object_id" {
  description = "returns a string"
  value       = data.azuread_service_principal.this.object_id
}

output "this" {
  value = azuread_service_principal.this
}
```

[top](#index)