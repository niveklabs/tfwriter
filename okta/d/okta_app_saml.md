# okta_app_saml

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app_saml" {
  source = "./modules/okta/d/okta_app_saml"

  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = null
  # accessibility_login_redirect_url - (optional) is a type of string
  accessibility_login_redirect_url = null
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = null
  # acs_endpoints - (optional) is a type of set of string
  acs_endpoints = []
  # active_only - (optional) is a type of bool
  active_only = null
  # app_settings_json - (optional) is a type of string
  app_settings_json = null
  # assertion_signed - (optional) is a type of bool
  assertion_signed = null
  # audience - (optional) is a type of string
  audience = null
  # authn_context_class_ref - (optional) is a type of string
  authn_context_class_ref = null
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = null
  # default_relay_state - (optional) is a type of string
  default_relay_state = null
  # destination - (optional) is a type of string
  destination = null
  # digest_algorithm - (optional) is a type of string
  digest_algorithm = null
  # features - (optional) is a type of set of string
  features = []
  # groups - (optional) is a type of set of string
  groups = []
  # hide_ios - (optional) is a type of bool
  hide_ios = null
  # hide_web - (optional) is a type of bool
  hide_web = null
  # honor_force_authn - (optional) is a type of bool
  honor_force_authn = null
  # idp_issuer - (optional) is a type of string
  idp_issuer = null
  # label - (optional) is a type of string
  label = null
  # label_prefix - (optional) is a type of string
  label_prefix = null
  # recipient - (optional) is a type of string
  recipient = null
  # request_compressed - (optional) is a type of bool
  request_compressed = null
  # response_signed - (optional) is a type of bool
  response_signed = null
  # signature_algorithm - (optional) is a type of string
  signature_algorithm = null
  # sp_issuer - (optional) is a type of string
  sp_issuer = null
  # sso_url - (optional) is a type of string
  sso_url = null
  # subject_name_id_format - (optional) is a type of string
  subject_name_id_format = null
  # subject_name_id_template - (optional) is a type of string
  subject_name_id_template = null
  # user_name_template - (optional) is a type of string
  user_name_template = null
  # user_name_template_suffix - (optional) is a type of string
  user_name_template_suffix = null
  # user_name_template_type - (optional) is a type of string
  user_name_template_type = null
  # users - (optional) is a type of set of string
  users = []

  attribute_statements = [{
    filter_type  = null
    filter_value = null
    name         = null
    namespace    = null
    type         = null
    values       = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accessibility_error_redirect_url" {
  description = "(optional) - Custom error page URL"
  type        = string
  default     = null
}

variable "accessibility_login_redirect_url" {
  description = "(optional) - Custom login page URL"
  type        = string
  default     = null
}

variable "accessibility_self_service" {
  description = "(optional) - Enable self service"
  type        = bool
  default     = null
}

variable "acs_endpoints" {
  description = "(optional) - List of ACS endpoints for this SAML application"
  type        = set(string)
  default     = null
}

variable "active_only" {
  description = "(optional) - Search only ACTIVE applications."
  type        = bool
  default     = null
}

variable "app_settings_json" {
  description = "(optional) - Application settings in JSON format"
  type        = string
  default     = null
}

variable "assertion_signed" {
  description = "(optional) - Determines whether the SAML assertion is digitally signed"
  type        = bool
  default     = null
}

variable "audience" {
  description = "(optional) - Audience Restriction"
  type        = string
  default     = null
}

variable "authn_context_class_ref" {
  description = "(optional) - Identifies the SAML authentication context class for the assertion’s authentication statement"
  type        = string
  default     = null
}

variable "auto_submit_toolbar" {
  description = "(optional) - Display auto submit toolbar"
  type        = bool
  default     = null
}

variable "default_relay_state" {
  description = "(optional) - Identifies a specific application resource in an IDP initiated SSO scenario."
  type        = string
  default     = null
}

variable "destination" {
  description = "(optional) - Identifies the location where the SAML response is intended to be sent inside of the SAML assertion"
  type        = string
  default     = null
}

variable "digest_algorithm" {
  description = "(optional) - Determines the digest algorithm used to digitally sign the SAML assertion and response"
  type        = string
  default     = null
}

variable "features" {
  description = "(optional) - features to enable"
  type        = set(string)
  default     = null
}

variable "groups" {
  description = "(optional) - Groups associated with the application"
  type        = set(string)
  default     = null
}

variable "hide_ios" {
  description = "(optional) - Do not display application icon on mobile app"
  type        = bool
  default     = null
}

variable "hide_web" {
  description = "(optional) - Do not display application icon to users"
  type        = bool
  default     = null
}

variable "honor_force_authn" {
  description = "(optional) - Prompt user to re-authenticate if SP asks for it"
  type        = bool
  default     = null
}

variable "idp_issuer" {
  description = "(optional) - SAML issuer ID"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recipient" {
  description = "(optional) - The location where the app may present the SAML assertion"
  type        = string
  default     = null
}

variable "request_compressed" {
  description = "(optional) - Denotes whether the request is compressed or not."
  type        = bool
  default     = null
}

variable "response_signed" {
  description = "(optional) - Determines whether the SAML auth response message is digitally signed"
  type        = bool
  default     = null
}

variable "signature_algorithm" {
  description = "(optional) - Signature algorithm used ot digitally sign the assertion and response"
  type        = string
  default     = null
}

variable "sp_issuer" {
  description = "(optional) - SAML SP issuer ID"
  type        = string
  default     = null
}

variable "sso_url" {
  description = "(optional) - Single Sign On URL"
  type        = string
  default     = null
}

variable "subject_name_id_format" {
  description = "(optional) - Identifies the SAML processing rules."
  type        = string
  default     = null
}

variable "subject_name_id_template" {
  description = "(optional) - Template for app user's username when a user is assigned to the app"
  type        = string
  default     = null
}

variable "user_name_template" {
  description = "(optional) - Username template"
  type        = string
  default     = null
}

variable "user_name_template_suffix" {
  description = "(optional) - Username template suffix"
  type        = string
  default     = null
}

variable "user_name_template_type" {
  description = "(optional) - Username template type"
  type        = string
  default     = null
}

variable "users" {
  description = "(optional) - Users associated with the application"
  type        = set(string)
  default     = null
}

variable "attribute_statements" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      filter_type  = string
      filter_value = string
      name         = string
      namespace    = string
      type         = string
      values       = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "okta_app_saml" "this" {
  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = var.accessibility_error_redirect_url
  # accessibility_login_redirect_url - (optional) is a type of string
  accessibility_login_redirect_url = var.accessibility_login_redirect_url
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = var.accessibility_self_service
  # acs_endpoints - (optional) is a type of set of string
  acs_endpoints = var.acs_endpoints
  # active_only - (optional) is a type of bool
  active_only = var.active_only
  # app_settings_json - (optional) is a type of string
  app_settings_json = var.app_settings_json
  # assertion_signed - (optional) is a type of bool
  assertion_signed = var.assertion_signed
  # audience - (optional) is a type of string
  audience = var.audience
  # authn_context_class_ref - (optional) is a type of string
  authn_context_class_ref = var.authn_context_class_ref
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = var.auto_submit_toolbar
  # default_relay_state - (optional) is a type of string
  default_relay_state = var.default_relay_state
  # destination - (optional) is a type of string
  destination = var.destination
  # digest_algorithm - (optional) is a type of string
  digest_algorithm = var.digest_algorithm
  # features - (optional) is a type of set of string
  features = var.features
  # groups - (optional) is a type of set of string
  groups = var.groups
  # hide_ios - (optional) is a type of bool
  hide_ios = var.hide_ios
  # hide_web - (optional) is a type of bool
  hide_web = var.hide_web
  # honor_force_authn - (optional) is a type of bool
  honor_force_authn = var.honor_force_authn
  # idp_issuer - (optional) is a type of string
  idp_issuer = var.idp_issuer
  # label - (optional) is a type of string
  label = var.label
  # label_prefix - (optional) is a type of string
  label_prefix = var.label_prefix
  # recipient - (optional) is a type of string
  recipient = var.recipient
  # request_compressed - (optional) is a type of bool
  request_compressed = var.request_compressed
  # response_signed - (optional) is a type of bool
  response_signed = var.response_signed
  # signature_algorithm - (optional) is a type of string
  signature_algorithm = var.signature_algorithm
  # sp_issuer - (optional) is a type of string
  sp_issuer = var.sp_issuer
  # sso_url - (optional) is a type of string
  sso_url = var.sso_url
  # subject_name_id_format - (optional) is a type of string
  subject_name_id_format = var.subject_name_id_format
  # subject_name_id_template - (optional) is a type of string
  subject_name_id_template = var.subject_name_id_template
  # user_name_template - (optional) is a type of string
  user_name_template = var.user_name_template
  # user_name_template_suffix - (optional) is a type of string
  user_name_template_suffix = var.user_name_template_suffix
  # user_name_template_type - (optional) is a type of string
  user_name_template_type = var.user_name_template_type
  # users - (optional) is a type of set of string
  users = var.users

  dynamic "attribute_statements" {
    for_each = var.attribute_statements
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_app_saml.this.id
}

output "key_id" {
  description = "returns a string"
  value       = data.okta_app_saml.this.key_id
}

output "links" {
  description = "returns a string"
  value       = data.okta_app_saml.this.links
}

output "name" {
  description = "returns a string"
  value       = data.okta_app_saml.this.name
}

output "single_logout_certificate" {
  description = "returns a string"
  value       = data.okta_app_saml.this.single_logout_certificate
}

output "single_logout_issuer" {
  description = "returns a string"
  value       = data.okta_app_saml.this.single_logout_issuer
}

output "single_logout_url" {
  description = "returns a string"
  value       = data.okta_app_saml.this.single_logout_url
}

output "status" {
  description = "returns a string"
  value       = data.okta_app_saml.this.status
}

output "this" {
  value = okta_app_saml.this
}
```

[top](#index)