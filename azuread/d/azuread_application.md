# azuread_application

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
    azuread = ">= 1.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_application" {
  source = "./modules/azuread/d/azuread_application"

  # application_id - (optional) is a type of string
  application_id = null
  # name - (optional) is a type of string
  name = null
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

  optional_claims = [{
    access_token = [{
      additional_properties = []
      essential             = null
      name                  = null
      source                = null
    }]
    id_token = [{
      additional_properties = []
      essential             = null
      name                  = null
      source                = null
    }]
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

variable "name" {
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

variable "optional_claims" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_token = list(object(
        {
          additional_properties = list(string)
          essential             = bool
          name                  = string
          source                = string
        }
      ))
      id_token = list(object(
        {
          additional_properties = list(string)
          essential             = bool
          name                  = string
          source                = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azuread_application" "this" {
  application_id = var.application_id
  name           = var.name
  object_id      = var.object_id

  dynamic "oauth2_permissions" {
    for_each = var.oauth2_permissions
    content {
    }
  }

  dynamic "optional_claims" {
    for_each = var.optional_claims
    content {

      dynamic "access_token" {
        for_each = optional_claims.value.access_token
        content {
          additional_properties = access_token.value["additional_properties"]
          essential             = access_token.value["essential"]
          name                  = access_token.value["name"]
          source                = access_token.value["source"]
        }
      }

      dynamic "id_token" {
        for_each = optional_claims.value.id_token
        content {
          additional_properties = id_token.value["additional_properties"]
          essential             = id_token.value["essential"]
          name                  = id_token.value["name"]
          source                = id_token.value["source"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_roles" {
  description = "returns a list of object"
  value       = data.azuread_application.this.app_roles
}

output "application_id" {
  description = "returns a string"
  value       = data.azuread_application.this.application_id
}

output "available_to_other_tenants" {
  description = "returns a bool"
  value       = data.azuread_application.this.available_to_other_tenants
}

output "group_membership_claims" {
  description = "returns a string"
  value       = data.azuread_application.this.group_membership_claims
}

output "homepage" {
  description = "returns a string"
  value       = data.azuread_application.this.homepage
}

output "id" {
  description = "returns a string"
  value       = data.azuread_application.this.id
}

output "identifier_uris" {
  description = "returns a list of string"
  value       = data.azuread_application.this.identifier_uris
}

output "logout_url" {
  description = "returns a string"
  value       = data.azuread_application.this.logout_url
}

output "name" {
  description = "returns a string"
  value       = data.azuread_application.this.name
}

output "oauth2_allow_implicit_flow" {
  description = "returns a bool"
  value       = data.azuread_application.this.oauth2_allow_implicit_flow
}

output "object_id" {
  description = "returns a string"
  value       = data.azuread_application.this.object_id
}

output "owners" {
  description = "returns a list of string"
  value       = data.azuread_application.this.owners
}

output "reply_urls" {
  description = "returns a list of string"
  value       = data.azuread_application.this.reply_urls
}

output "required_resource_access" {
  description = "returns a list of object"
  value       = data.azuread_application.this.required_resource_access
}

output "type" {
  description = "returns a string"
  value       = data.azuread_application.this.type
}

output "this" {
  value = azuread_application.this
}
```

[top](#index)