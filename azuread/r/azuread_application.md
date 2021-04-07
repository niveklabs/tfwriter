# azuread_application

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
module "azuread_application" {
  source = "./modules/azuread/r/azuread_application"

  # app_role - (optional) is a type of set of object
  app_role = [{
    allowed_member_types = []
    description          = null
    display_name         = null
    id                   = null
    is_enabled           = null
    value                = null
  }]
  # available_to_other_tenants - (optional) is a type of bool
  available_to_other_tenants = null
  # display_name - (optional) is a type of string
  display_name = null
  # group_membership_claims - (optional) is a type of string
  group_membership_claims = null
  # homepage - (optional) is a type of string
  homepage = null
  # identifier_uris - (optional) is a type of list of string
  identifier_uris = []
  # logout_url - (optional) is a type of string
  logout_url = null
  # name - (optional) is a type of string
  name = null
  # oauth2_allow_implicit_flow - (optional) is a type of bool
  oauth2_allow_implicit_flow = null
  # oauth2_permissions - (optional) is a type of set of object
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
  # owners - (optional) is a type of set of string
  owners = []
  # prevent_duplicate_names - (optional) is a type of bool
  prevent_duplicate_names = null
  # public_client - (optional) is a type of bool
  public_client = null
  # reply_urls - (optional) is a type of set of string
  reply_urls = []
  # type - (optional) is a type of string
  type = null

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

  required_resource_access = [{
    resource_access = [{
      id   = null
      type = null
    }]
    resource_app_id = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_role" {
  description = "(optional)"
  type = set(object(
    {
      allowed_member_types = set(string)
      description          = string
      display_name         = string
      id                   = string
      is_enabled           = bool
      value                = string
    }
  ))
  default = null
}

variable "available_to_other_tenants" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_membership_claims" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "homepage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier_uris" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "logout_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oauth2_allow_implicit_flow" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "oauth2_permissions" {
  description = "(optional)"
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
  default = null
}

variable "owners" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "prevent_duplicate_names" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "public_client" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "reply_urls" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "required_resource_access" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      resource_access = list(object(
        {
          id   = string
          type = string
        }
      ))
      resource_app_id = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuread_application" "this" {
  # app_role - (optional) is a type of set of object
  app_role = var.app_role
  # available_to_other_tenants - (optional) is a type of bool
  available_to_other_tenants = var.available_to_other_tenants
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # group_membership_claims - (optional) is a type of string
  group_membership_claims = var.group_membership_claims
  # homepage - (optional) is a type of string
  homepage = var.homepage
  # identifier_uris - (optional) is a type of list of string
  identifier_uris = var.identifier_uris
  # logout_url - (optional) is a type of string
  logout_url = var.logout_url
  # name - (optional) is a type of string
  name = var.name
  # oauth2_allow_implicit_flow - (optional) is a type of bool
  oauth2_allow_implicit_flow = var.oauth2_allow_implicit_flow
  # oauth2_permissions - (optional) is a type of set of object
  oauth2_permissions = var.oauth2_permissions
  # owners - (optional) is a type of set of string
  owners = var.owners
  # prevent_duplicate_names - (optional) is a type of bool
  prevent_duplicate_names = var.prevent_duplicate_names
  # public_client - (optional) is a type of bool
  public_client = var.public_client
  # reply_urls - (optional) is a type of set of string
  reply_urls = var.reply_urls
  # type - (optional) is a type of string
  type = var.type

  dynamic "optional_claims" {
    for_each = var.optional_claims
    content {

      dynamic "access_token" {
        for_each = optional_claims.value.access_token
        content {
          # additional_properties - (optional) is a type of list of string
          additional_properties = access_token.value["additional_properties"]
          # essential - (optional) is a type of bool
          essential = access_token.value["essential"]
          # name - (required) is a type of string
          name = access_token.value["name"]
          # source - (optional) is a type of string
          source = access_token.value["source"]
        }
      }

      dynamic "id_token" {
        for_each = optional_claims.value.id_token
        content {
          # additional_properties - (optional) is a type of list of string
          additional_properties = id_token.value["additional_properties"]
          # essential - (optional) is a type of bool
          essential = id_token.value["essential"]
          # name - (required) is a type of string
          name = id_token.value["name"]
          # source - (optional) is a type of string
          source = id_token.value["source"]
        }
      }

    }
  }

  dynamic "required_resource_access" {
    for_each = var.required_resource_access
    content {
      # resource_app_id - (required) is a type of string
      resource_app_id = required_resource_access.value["resource_app_id"]

      dynamic "resource_access" {
        for_each = required_resource_access.value.resource_access
        content {
          # id - (required) is a type of string
          id = resource_access.value["id"]
          # type - (required) is a type of string
          type = resource_access.value["type"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_role" {
  description = "returns a set of object"
  value       = azuread_application.this.app_role
}

output "application_id" {
  description = "returns a string"
  value       = azuread_application.this.application_id
}

output "display_name" {
  description = "returns a string"
  value       = azuread_application.this.display_name
}

output "homepage" {
  description = "returns a string"
  value       = azuread_application.this.homepage
}

output "id" {
  description = "returns a string"
  value       = azuread_application.this.id
}

output "identifier_uris" {
  description = "returns a list of string"
  value       = azuread_application.this.identifier_uris
}

output "name" {
  description = "returns a string"
  value       = azuread_application.this.name
}

output "oauth2_permissions" {
  description = "returns a set of object"
  value       = azuread_application.this.oauth2_permissions
}

output "object_id" {
  description = "returns a string"
  value       = azuread_application.this.object_id
}

output "owners" {
  description = "returns a set of string"
  value       = azuread_application.this.owners
}

output "public_client" {
  description = "returns a bool"
  value       = azuread_application.this.public_client
}

output "reply_urls" {
  description = "returns a set of string"
  value       = azuread_application.this.reply_urls
}

output "this" {
  value = azuread_application.this
}
```

[top](#index)