# onelogin_saml_apps

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_saml_apps" {
  source = "./modules/onelogin/r/onelogin_saml_apps"

  # allow_assumed_signin - (optional) is a type of bool
  allow_assumed_signin = null
  # brand_id - (optional) is a type of number
  brand_id = null
  # configuration - (optional) is a type of map of string
  configuration = {}
  # connector_id - (required) is a type of number
  connector_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # provisioning - (optional) is a type of map of bool
  provisioning = {}
  # visible - (optional) is a type of bool
  visible = null

  parameters = [{
    attributes_transformations = null
    default_values             = null
    include_in_saml_assertion  = null
    label                      = null
    param_id                   = null
    param_key_name             = null
    provisioned_entitlements   = null
    safe_entitlements_enabled  = null
    skip_if_blank              = null
    user_attribute_macros      = null
    user_attribute_mappings    = null
    values                     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_assumed_signin" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "brand_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "configuration" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "connector_id" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provisioning" {
  description = "(optional)"
  type        = map(bool)
  default     = null
}

variable "visible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      attributes_transformations = string
      default_values             = string
      include_in_saml_assertion  = bool
      label                      = string
      param_id                   = number
      param_key_name             = string
      provisioned_entitlements   = bool
      safe_entitlements_enabled  = bool
      skip_if_blank              = bool
      user_attribute_macros      = string
      user_attribute_mappings    = string
      values                     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_saml_apps" "this" {
  allow_assumed_signin = var.allow_assumed_signin
  brand_id             = var.brand_id
  configuration        = var.configuration
  connector_id         = var.connector_id
  description          = var.description
  name                 = var.name
  notes                = var.notes
  provisioning         = var.provisioning
  visible              = var.visible

  dynamic "parameters" {
    for_each = var.parameters
    content {
      attributes_transformations = parameters.value["attributes_transformations"]
      default_values             = parameters.value["default_values"]
      include_in_saml_assertion  = parameters.value["include_in_saml_assertion"]
      label                      = parameters.value["label"]
      param_key_name             = parameters.value["param_key_name"]
      provisioned_entitlements   = parameters.value["provisioned_entitlements"]
      safe_entitlements_enabled  = parameters.value["safe_entitlements_enabled"]
      skip_if_blank              = parameters.value["skip_if_blank"]
      user_attribute_macros      = parameters.value["user_attribute_macros"]
      user_attribute_mappings    = parameters.value["user_attribute_mappings"]
      values                     = parameters.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_method" {
  description = "returns a number"
  value       = onelogin_saml_apps.this.auth_method
}

output "certificate" {
  description = "returns a map of string"
  value       = onelogin_saml_apps.this.certificate
}

output "created_at" {
  description = "returns a string"
  value       = onelogin_saml_apps.this.created_at
}

output "icon_url" {
  description = "returns a string"
  value       = onelogin_saml_apps.this.icon_url
}

output "id" {
  description = "returns a string"
  value       = onelogin_saml_apps.this.id
}

output "policy_id" {
  description = "returns a number"
  value       = onelogin_saml_apps.this.policy_id
}

output "provisioning" {
  description = "returns a map of bool"
  value       = onelogin_saml_apps.this.provisioning
}

output "sso" {
  description = "returns a map of string"
  value       = onelogin_saml_apps.this.sso
}

output "tab_id" {
  description = "returns a number"
  value       = onelogin_saml_apps.this.tab_id
}

output "updated_at" {
  description = "returns a string"
  value       = onelogin_saml_apps.this.updated_at
}

output "this" {
  value = onelogin_saml_apps.this
}
```

[top](#index)