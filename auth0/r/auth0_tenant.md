# auth0_tenant

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_tenant" {
  source = "./modules/auth0/r/auth0_tenant"

  # allowed_logout_urls - (optional) is a type of list of string
  allowed_logout_urls = []
  # default_audience - (optional) is a type of string
  default_audience = null
  # default_directory - (optional) is a type of string
  default_directory = null
  # default_redirection_uri - (optional) is a type of string
  default_redirection_uri = null
  # enabled_locales - (optional) is a type of set of string
  enabled_locales = []
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # idle_session_lifetime - (optional) is a type of number
  idle_session_lifetime = null
  # picture_url - (optional) is a type of string
  picture_url = null
  # sandbox_version - (optional) is a type of string
  sandbox_version = null
  # session_lifetime - (optional) is a type of number
  session_lifetime = null
  # support_email - (optional) is a type of string
  support_email = null
  # support_url - (optional) is a type of string
  support_url = null

  change_password = [{
    enabled = null
    html    = null
  }]

  error_page = [{
    html          = null
    show_log_link = null
    url           = null
  }]

  flags = [{
    change_pwd_flow_v1                     = null
    disable_clickjack_protection_headers   = null
    enable_apis_section                    = null
    enable_client_connections              = null
    enable_custom_domain_in_emails         = null
    enable_dynamic_client_registration     = null
    enable_legacy_logs_search_v2           = null
    enable_pipeline2                       = null
    enable_public_signup_user_exists_error = null
    universal_login                        = null
    use_scope_descriptions_for_consent     = null
  }]

  guardian_mfa_page = [{
    enabled = null
    html    = null
  }]

  universal_login = [{
    colors = [{
      page_background = null
      primary         = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowed_logout_urls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "default_audience" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_directory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_redirection_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled_locales" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "friendly_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idle_session_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "picture_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sandbox_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "support_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "support_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "change_password" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      html    = string
    }
  ))
  default = []
}

variable "error_page" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      html          = string
      show_log_link = bool
      url           = string
    }
  ))
  default = []
}

variable "flags" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      change_pwd_flow_v1                     = bool
      disable_clickjack_protection_headers   = bool
      enable_apis_section                    = bool
      enable_client_connections              = bool
      enable_custom_domain_in_emails         = bool
      enable_dynamic_client_registration     = bool
      enable_legacy_logs_search_v2           = bool
      enable_pipeline2                       = bool
      enable_public_signup_user_exists_error = bool
      universal_login                        = bool
      use_scope_descriptions_for_consent     = bool
    }
  ))
  default = []
}

variable "guardian_mfa_page" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      html    = string
    }
  ))
  default = []
}

variable "universal_login" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      colors = list(object(
        {
          page_background = string
          primary         = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "auth0_tenant" "this" {
  # allowed_logout_urls - (optional) is a type of list of string
  allowed_logout_urls = var.allowed_logout_urls
  # default_audience - (optional) is a type of string
  default_audience = var.default_audience
  # default_directory - (optional) is a type of string
  default_directory = var.default_directory
  # default_redirection_uri - (optional) is a type of string
  default_redirection_uri = var.default_redirection_uri
  # enabled_locales - (optional) is a type of set of string
  enabled_locales = var.enabled_locales
  # friendly_name - (optional) is a type of string
  friendly_name = var.friendly_name
  # idle_session_lifetime - (optional) is a type of number
  idle_session_lifetime = var.idle_session_lifetime
  # picture_url - (optional) is a type of string
  picture_url = var.picture_url
  # sandbox_version - (optional) is a type of string
  sandbox_version = var.sandbox_version
  # session_lifetime - (optional) is a type of number
  session_lifetime = var.session_lifetime
  # support_email - (optional) is a type of string
  support_email = var.support_email
  # support_url - (optional) is a type of string
  support_url = var.support_url

  dynamic "change_password" {
    for_each = var.change_password
    content {
      # enabled - (required) is a type of bool
      enabled = change_password.value["enabled"]
      # html - (required) is a type of string
      html = change_password.value["html"]
    }
  }

  dynamic "error_page" {
    for_each = var.error_page
    content {
      # html - (required) is a type of string
      html = error_page.value["html"]
      # show_log_link - (required) is a type of bool
      show_log_link = error_page.value["show_log_link"]
      # url - (required) is a type of string
      url = error_page.value["url"]
    }
  }

  dynamic "flags" {
    for_each = var.flags
    content {
      # change_pwd_flow_v1 - (optional) is a type of bool
      change_pwd_flow_v1 = flags.value["change_pwd_flow_v1"]
      # disable_clickjack_protection_headers - (optional) is a type of bool
      disable_clickjack_protection_headers = flags.value["disable_clickjack_protection_headers"]
      # enable_apis_section - (optional) is a type of bool
      enable_apis_section = flags.value["enable_apis_section"]
      # enable_client_connections - (optional) is a type of bool
      enable_client_connections = flags.value["enable_client_connections"]
      # enable_custom_domain_in_emails - (optional) is a type of bool
      enable_custom_domain_in_emails = flags.value["enable_custom_domain_in_emails"]
      # enable_dynamic_client_registration - (optional) is a type of bool
      enable_dynamic_client_registration = flags.value["enable_dynamic_client_registration"]
      # enable_legacy_logs_search_v2 - (optional) is a type of bool
      enable_legacy_logs_search_v2 = flags.value["enable_legacy_logs_search_v2"]
      # enable_pipeline2 - (optional) is a type of bool
      enable_pipeline2 = flags.value["enable_pipeline2"]
      # enable_public_signup_user_exists_error - (optional) is a type of bool
      enable_public_signup_user_exists_error = flags.value["enable_public_signup_user_exists_error"]
      # universal_login - (optional) is a type of bool
      universal_login = flags.value["universal_login"]
      # use_scope_descriptions_for_consent - (optional) is a type of bool
      use_scope_descriptions_for_consent = flags.value["use_scope_descriptions_for_consent"]
    }
  }

  dynamic "guardian_mfa_page" {
    for_each = var.guardian_mfa_page
    content {
      # enabled - (required) is a type of bool
      enabled = guardian_mfa_page.value["enabled"]
      # html - (required) is a type of string
      html = guardian_mfa_page.value["html"]
    }
  }

  dynamic "universal_login" {
    for_each = var.universal_login
    content {

      dynamic "colors" {
        for_each = universal_login.value.colors
        content {
          # page_background - (optional) is a type of string
          page_background = colors.value["page_background"]
          # primary - (optional) is a type of string
          primary = colors.value["primary"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allowed_logout_urls" {
  description = "returns a list of string"
  value       = auth0_tenant.this.allowed_logout_urls
}

output "default_audience" {
  description = "returns a string"
  value       = auth0_tenant.this.default_audience
}

output "default_directory" {
  description = "returns a string"
  value       = auth0_tenant.this.default_directory
}

output "default_redirection_uri" {
  description = "returns a string"
  value       = auth0_tenant.this.default_redirection_uri
}

output "enabled_locales" {
  description = "returns a set of string"
  value       = auth0_tenant.this.enabled_locales
}

output "friendly_name" {
  description = "returns a string"
  value       = auth0_tenant.this.friendly_name
}

output "id" {
  description = "returns a string"
  value       = auth0_tenant.this.id
}

output "idle_session_lifetime" {
  description = "returns a number"
  value       = auth0_tenant.this.idle_session_lifetime
}

output "picture_url" {
  description = "returns a string"
  value       = auth0_tenant.this.picture_url
}

output "sandbox_version" {
  description = "returns a string"
  value       = auth0_tenant.this.sandbox_version
}

output "session_lifetime" {
  description = "returns a number"
  value       = auth0_tenant.this.session_lifetime
}

output "support_email" {
  description = "returns a string"
  value       = auth0_tenant.this.support_email
}

output "support_url" {
  description = "returns a string"
  value       = auth0_tenant.this.support_url
}

output "this" {
  value = auth0_tenant.this
}
```

[top](#index)