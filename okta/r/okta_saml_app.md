# okta_saml_app

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "okta_saml_app" {
  source = "./modules/okta/r/okta_saml_app"

  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = null
  # accessibility_login_redirect_url - (optional) is a type of string
  accessibility_login_redirect_url = null
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = null
  # acs_endpoints - (optional) is a type of set of string
  acs_endpoints = []
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
  # key_name - (optional) is a type of string
  key_name = null
  # key_years_valid - (optional) is a type of number
  key_years_valid = null
  # label - (required) is a type of string
  label = null
  # preconfigured_app - (optional) is a type of string
  preconfigured_app = null
  # recipient - (optional) is a type of string
  recipient = null
  # request_compressed - (optional) is a type of bool
  request_compressed = null
  # response_signed - (optional) is a type of bool
  response_signed = null
  # signature_algorithm - (optional) is a type of string
  signature_algorithm = null
  # single_logout_certificate - (optional) is a type of string
  single_logout_certificate = null
  # single_logout_issuer - (optional) is a type of string
  single_logout_issuer = null
  # single_logout_url - (optional) is a type of string
  single_logout_url = null
  # sp_issuer - (optional) is a type of string
  sp_issuer = null
  # sso_url - (optional) is a type of string
  sso_url = null
  # status - (optional) is a type of string
  status = null
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

  attribute_statements = [{
    filter_type  = null
    filter_value = null
    name         = null
    namespace    = null
    type         = null
    values       = []
  }]

  users = [{
    id       = null
    password = null
    scope    = null
    username = null
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

variable "key_name" {
  description = "(optional) - Certificate name. This modulates the rotation of keys. New name == new key."
  type        = string
  default     = null
}

variable "key_years_valid" {
  description = "(optional) - Number of years the certificate is valid."
  type        = number
  default     = null
}

variable "label" {
  description = "(required) - Pretty name of app."
  type        = string
}

variable "preconfigured_app" {
  description = "(optional) - Name of preexisting SAML application. For instance 'slack'"
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

variable "single_logout_certificate" {
  description = "(optional) - x509 encoded certificate that the Service Provider uses to sign Single Logout requests"
  type        = string
  default     = null
}

variable "single_logout_issuer" {
  description = "(optional) - The issuer of the Service Provider that generates the Single Logout request"
  type        = string
  default     = null
}

variable "single_logout_url" {
  description = "(optional) - The location where the logout response is sent"
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

variable "status" {
  description = "(optional) - Status of application."
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

variable "users" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id       = string
      password = string
      scope    = string
      username = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_saml_app" "this" {
  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = var.accessibility_error_redirect_url
  # accessibility_login_redirect_url - (optional) is a type of string
  accessibility_login_redirect_url = var.accessibility_login_redirect_url
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = var.accessibility_self_service
  # acs_endpoints - (optional) is a type of set of string
  acs_endpoints = var.acs_endpoints
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
  # key_name - (optional) is a type of string
  key_name = var.key_name
  # key_years_valid - (optional) is a type of number
  key_years_valid = var.key_years_valid
  # label - (required) is a type of string
  label = var.label
  # preconfigured_app - (optional) is a type of string
  preconfigured_app = var.preconfigured_app
  # recipient - (optional) is a type of string
  recipient = var.recipient
  # request_compressed - (optional) is a type of bool
  request_compressed = var.request_compressed
  # response_signed - (optional) is a type of bool
  response_signed = var.response_signed
  # signature_algorithm - (optional) is a type of string
  signature_algorithm = var.signature_algorithm
  # single_logout_certificate - (optional) is a type of string
  single_logout_certificate = var.single_logout_certificate
  # single_logout_issuer - (optional) is a type of string
  single_logout_issuer = var.single_logout_issuer
  # single_logout_url - (optional) is a type of string
  single_logout_url = var.single_logout_url
  # sp_issuer - (optional) is a type of string
  sp_issuer = var.sp_issuer
  # sso_url - (optional) is a type of string
  sso_url = var.sso_url
  # status - (optional) is a type of string
  status = var.status
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

  dynamic "attribute_statements" {
    for_each = var.attribute_statements
    content {
      # filter_type - (optional) is a type of string
      filter_type = attribute_statements.value["filter_type"]
      # filter_value - (optional) is a type of string
      filter_value = attribute_statements.value["filter_value"]
      # name - (required) is a type of string
      name = attribute_statements.value["name"]
      # namespace - (optional) is a type of string
      namespace = attribute_statements.value["namespace"]
      # type - (optional) is a type of string
      type = attribute_statements.value["type"]
      # values - (optional) is a type of list of string
      values = attribute_statements.value["values"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
      # id - (optional) is a type of string
      id = users.value["id"]
      # password - (optional) is a type of string
      password = users.value["password"]
      # username - (optional) is a type of string
      username = users.value["username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = okta_saml_app.this.certificate
}

output "entity_key" {
  description = "returns a string"
  value       = okta_saml_app.this.entity_key
}

output "entity_url" {
  description = "returns a string"
  value       = okta_saml_app.this.entity_url
}

output "http_post_binding" {
  description = "returns a string"
  value       = okta_saml_app.this.http_post_binding
}

output "http_redirect_binding" {
  description = "returns a string"
  value       = okta_saml_app.this.http_redirect_binding
}

output "id" {
  description = "returns a string"
  value       = okta_saml_app.this.id
}

output "key_id" {
  description = "returns a string"
  value       = okta_saml_app.this.key_id
}

output "metadata" {
  description = "returns a string"
  value       = okta_saml_app.this.metadata
}

output "metadata_url" {
  description = "returns a string"
  value       = okta_saml_app.this.metadata_url
}

output "name" {
  description = "returns a string"
  value       = okta_saml_app.this.name
}

output "sign_on_mode" {
  description = "returns a string"
  value       = okta_saml_app.this.sign_on_mode
}

output "this" {
  value = okta_saml_app.this
}
```

[top](#index)