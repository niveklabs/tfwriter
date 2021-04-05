# sumologic_saml_configuration

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_saml_configuration" {
  source = "./modules/sumologic/r/sumologic_saml_configuration"

  # authn_request_url - (optional) is a type of string
  authn_request_url = null
  # configuration_name - (required) is a type of string
  configuration_name = null
  # debug_mode - (optional) is a type of bool
  debug_mode = null
  # disable_requested_authn_context - (optional) is a type of bool
  disable_requested_authn_context = null
  # email_attribute - (optional) is a type of string
  email_attribute = null
  # is_redirect_binding - (optional) is a type of bool
  is_redirect_binding = null
  # issuer - (required) is a type of string
  issuer = null
  # logout_enabled - (optional) is a type of bool
  logout_enabled = null
  # logout_url - (optional) is a type of string
  logout_url = null
  # roles_attribute - (optional) is a type of string
  roles_attribute = null
  # sign_authn_request - (optional) is a type of bool
  sign_authn_request = null
  # sp_initiated_login_enabled - (optional) is a type of bool
  sp_initiated_login_enabled = null
  # sp_initiated_login_path - (optional) is a type of string
  sp_initiated_login_path = null
  # x509cert1 - (required) is a type of string
  x509cert1 = null
  # x509cert2 - (optional) is a type of string
  x509cert2 = null
  # x509cert3 - (optional) is a type of string
  x509cert3 = null

  on_demand_provisioning_enabled = [{
    first_name_attribute         = null
    last_name_attribute          = null
    on_demand_provisioning_roles = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authn_request_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configuration_name" {
  description = "(required)"
  type        = string
}

variable "debug_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_requested_authn_context" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_redirect_binding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "issuer" {
  description = "(required)"
  type        = string
}

variable "logout_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "logout_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roles_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sign_authn_request" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sp_initiated_login_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sp_initiated_login_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "x509cert1" {
  description = "(required)"
  type        = string
}

variable "x509cert2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "x509cert3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "on_demand_provisioning_enabled" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      first_name_attribute         = string
      last_name_attribute          = string
      on_demand_provisioning_roles = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_saml_configuration" "this" {
  authn_request_url               = var.authn_request_url
  configuration_name              = var.configuration_name
  debug_mode                      = var.debug_mode
  disable_requested_authn_context = var.disable_requested_authn_context
  email_attribute                 = var.email_attribute
  is_redirect_binding             = var.is_redirect_binding
  issuer                          = var.issuer
  logout_enabled                  = var.logout_enabled
  logout_url                      = var.logout_url
  roles_attribute                 = var.roles_attribute
  sign_authn_request              = var.sign_authn_request
  sp_initiated_login_enabled      = var.sp_initiated_login_enabled
  sp_initiated_login_path         = var.sp_initiated_login_path
  x509cert1                       = var.x509cert1
  x509cert2                       = var.x509cert2
  x509cert3                       = var.x509cert3

  dynamic "on_demand_provisioning_enabled" {
    for_each = var.on_demand_provisioning_enabled
    content {
      first_name_attribute         = on_demand_provisioning_enabled.value["first_name_attribute"]
      last_name_attribute          = on_demand_provisioning_enabled.value["last_name_attribute"]
      on_demand_provisioning_roles = on_demand_provisioning_enabled.value["on_demand_provisioning_roles"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = sumologic_saml_configuration.this.certificate
}

output "id" {
  description = "returns a string"
  value       = sumologic_saml_configuration.this.id
}

output "this" {
  value = sumologic_saml_configuration.this
}
```

[top](#index)