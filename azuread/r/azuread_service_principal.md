# azuread_service_principal

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
module "azuread_service_principal" {
  source = "./modules/azuread/r/azuread_service_principal"

  # app_role_assignment_required - (optional) is a type of bool
  app_role_assignment_required = null
  # application_id - (required) is a type of string
  application_id = null
  # tags - (optional) is a type of set of string
  tags = []

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
variable "app_role_assignment_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "application_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
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

### Resource

```terraform
resource "azuread_service_principal" "this" {
  app_role_assignment_required = var.app_role_assignment_required
  application_id               = var.application_id
  tags                         = var.tags

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
output "display_name" {
  description = "returns a string"
  value       = azuread_service_principal.this.display_name
}

output "id" {
  description = "returns a string"
  value       = azuread_service_principal.this.id
}

output "object_id" {
  description = "returns a string"
  value       = azuread_service_principal.this.object_id
}

output "this" {
  value = azuread_service_principal.this
}
```

[top](#index)