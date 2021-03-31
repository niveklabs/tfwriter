# fortios_system_saml

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_saml" {
  source = "./modules/fortios/r/fortios_system_saml"

  # cert - (optional) is a type of string
  cert = null
  # default_login_page - (optional) is a type of string
  default_login_page = null
  # default_profile - (optional) is a type of string
  default_profile = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # entity_id - (optional) is a type of string
  entity_id = null
  # idp_cert - (optional) is a type of string
  idp_cert = null
  # idp_entity_id - (optional) is a type of string
  idp_entity_id = null
  # idp_single_logout_url - (optional) is a type of string
  idp_single_logout_url = null
  # idp_single_sign_on_url - (optional) is a type of string
  idp_single_sign_on_url = null
  # life - (optional) is a type of number
  life = null
  # portal_url - (optional) is a type of string
  portal_url = null
  # role - (optional) is a type of string
  role = null
  # server_address - (optional) is a type of string
  server_address = null
  # single_logout_url - (optional) is a type of string
  single_logout_url = null
  # single_sign_on_url - (optional) is a type of string
  single_sign_on_url = null
  # status - (optional) is a type of string
  status = null
  # tolerance - (optional) is a type of number
  tolerance = null

  service_providers = [{
    assertion_attributes = [{
      name = null
      type = null
    }]
    idp_entity_id          = null
    idp_single_logout_url  = null
    idp_single_sign_on_url = null
    name                   = null
    prefix                 = null
    sp_cert                = null
    sp_entity_id           = null
    sp_portal_url          = null
    sp_single_logout_url   = null
    sp_single_sign_on_url  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_login_page" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entity_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_entity_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_single_logout_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_single_sign_on_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "life" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "portal_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_logout_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_sign_on_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tolerance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_providers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      assertion_attributes = list(object(
        {
          name = string
          type = string
        }
      ))
      idp_entity_id          = string
      idp_single_logout_url  = string
      idp_single_sign_on_url = string
      name                   = string
      prefix                 = string
      sp_cert                = string
      sp_entity_id           = string
      sp_portal_url          = string
      sp_single_logout_url   = string
      sp_single_sign_on_url  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_saml" "this" {
  cert                   = var.cert
  default_login_page     = var.default_login_page
  default_profile        = var.default_profile
  dynamic_sort_subtable  = var.dynamic_sort_subtable
  entity_id              = var.entity_id
  idp_cert               = var.idp_cert
  idp_entity_id          = var.idp_entity_id
  idp_single_logout_url  = var.idp_single_logout_url
  idp_single_sign_on_url = var.idp_single_sign_on_url
  life                   = var.life
  portal_url             = var.portal_url
  role                   = var.role
  server_address         = var.server_address
  single_logout_url      = var.single_logout_url
  single_sign_on_url     = var.single_sign_on_url
  status                 = var.status
  tolerance              = var.tolerance

  dynamic "service_providers" {
    for_each = var.service_providers
    content {
      idp_entity_id          = service_providers.value["idp_entity_id"]
      idp_single_logout_url  = service_providers.value["idp_single_logout_url"]
      idp_single_sign_on_url = service_providers.value["idp_single_sign_on_url"]
      name                   = service_providers.value["name"]
      prefix                 = service_providers.value["prefix"]
      sp_cert                = service_providers.value["sp_cert"]
      sp_entity_id           = service_providers.value["sp_entity_id"]
      sp_portal_url          = service_providers.value["sp_portal_url"]
      sp_single_logout_url   = service_providers.value["sp_single_logout_url"]
      sp_single_sign_on_url  = service_providers.value["sp_single_sign_on_url"]

      dynamic "assertion_attributes" {
        for_each = service_providers.value.assertion_attributes
        content {
          name = assertion_attributes.value["name"]
          type = assertion_attributes.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cert" {
  description = "returns a string"
  value       = fortios_system_saml.this.cert
}

output "default_login_page" {
  description = "returns a string"
  value       = fortios_system_saml.this.default_login_page
}

output "default_profile" {
  description = "returns a string"
  value       = fortios_system_saml.this.default_profile
}

output "entity_id" {
  description = "returns a string"
  value       = fortios_system_saml.this.entity_id
}

output "id" {
  description = "returns a string"
  value       = fortios_system_saml.this.id
}

output "idp_cert" {
  description = "returns a string"
  value       = fortios_system_saml.this.idp_cert
}

output "idp_entity_id" {
  description = "returns a string"
  value       = fortios_system_saml.this.idp_entity_id
}

output "idp_single_logout_url" {
  description = "returns a string"
  value       = fortios_system_saml.this.idp_single_logout_url
}

output "idp_single_sign_on_url" {
  description = "returns a string"
  value       = fortios_system_saml.this.idp_single_sign_on_url
}

output "life" {
  description = "returns a number"
  value       = fortios_system_saml.this.life
}

output "portal_url" {
  description = "returns a string"
  value       = fortios_system_saml.this.portal_url
}

output "role" {
  description = "returns a string"
  value       = fortios_system_saml.this.role
}

output "server_address" {
  description = "returns a string"
  value       = fortios_system_saml.this.server_address
}

output "single_logout_url" {
  description = "returns a string"
  value       = fortios_system_saml.this.single_logout_url
}

output "single_sign_on_url" {
  description = "returns a string"
  value       = fortios_system_saml.this.single_sign_on_url
}

output "status" {
  description = "returns a string"
  value       = fortios_system_saml.this.status
}

output "tolerance" {
  description = "returns a number"
  value       = fortios_system_saml.this.tolerance
}

output "this" {
  value = fortios_system_saml.this
}
```

[top](#index)