# okta_oauth_app

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
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_oauth_app" {
  source = "./modules/okta/r/okta_oauth_app"

  # auto_key_rotation - (optional) is a type of bool
  auto_key_rotation = null
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = null
  # client_basic_secret - (optional) is a type of string
  client_basic_secret = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_uri - (optional) is a type of string
  client_uri = null
  # consent_method - (optional) is a type of string
  consent_method = null
  # custom_client_id - (optional) is a type of string
  custom_client_id = null
  # grant_types - (optional) is a type of set of string
  grant_types = []
  # groups - (optional) is a type of set of string
  groups = []
  # hide_ios - (optional) is a type of bool
  hide_ios = null
  # hide_web - (optional) is a type of bool
  hide_web = null
  # issuer_mode - (optional) is a type of string
  issuer_mode = null
  # label - (required) is a type of string
  label = null
  # login_uri - (optional) is a type of string
  login_uri = null
  # logo_uri - (optional) is a type of string
  logo_uri = null
  # omit_secret - (optional) is a type of bool
  omit_secret = null
  # policy_uri - (optional) is a type of string
  policy_uri = null
  # post_logout_redirect_uris - (optional) is a type of set of string
  post_logout_redirect_uris = []
  # profile - (optional) is a type of string
  profile = null
  # redirect_uris - (optional) is a type of set of string
  redirect_uris = []
  # response_types - (optional) is a type of set of string
  response_types = []
  # status - (optional) is a type of string
  status = null
  # token_endpoint_auth_method - (optional) is a type of string
  token_endpoint_auth_method = null
  # tos_uri - (optional) is a type of string
  tos_uri = null
  # type - (required) is a type of string
  type = null

  jwks = [{
    e   = null
    kid = null
    kty = null
    n   = null
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
variable "auto_key_rotation" {
  description = "(optional) - Requested key rotation mode."
  type        = bool
  default     = null
}

variable "auto_submit_toolbar" {
  description = "(optional) - Display auto submit toolbar"
  type        = bool
  default     = null
}

variable "client_basic_secret" {
  description = "(optional) - OAuth client secret key, this can be set when token_endpoint_auth_method is client_secret_basic."
  type        = string
  default     = null
}

variable "client_id" {
  description = "(optional) - OAuth client ID. If set during creation, app is created with this id."
  type        = string
  default     = null
}

variable "client_uri" {
  description = "(optional) - URI to a web page providing information about the client."
  type        = string
  default     = null
}

variable "consent_method" {
  description = "(optional) - *Early Access Property*. Indicates whether user consent is required or implicit. Valid values: REQUIRED, TRUSTED. Default value is TRUSTED"
  type        = string
  default     = null
}

variable "custom_client_id" {
  description = "(optional) - **Deprecated** This property allows you to set your client_id during creation. NOTE: updating after creation will be a no-op, use client_id for that behavior instead."
  type        = string
  default     = null
}

variable "grant_types" {
  description = "(optional) - List of OAuth 2.0 grant types. Conditional validation params found here https://developer.okta.com/docs/api/resources/apps#credentials-settings-details. Defaults to minimum requirements per app type."
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

variable "issuer_mode" {
  description = "(optional) - *Early Access Property*. Indicates whether the Okta Authorization Server uses the original Okta org domain URL or a custom domain URL as the issuer of ID token for this client."
  type        = string
  default     = null
}

variable "label" {
  description = "(required) - Pretty name of app."
  type        = string
}

variable "login_uri" {
  description = "(optional) - URI that initiates login."
  type        = string
  default     = null
}

variable "logo_uri" {
  description = "(optional) - URI that references a logo for the client."
  type        = string
  default     = null
}

variable "omit_secret" {
  description = "(optional) - This tells the provider not to persist the application's secret to state. If this is ever changes from true => false your app will be recreated."
  type        = bool
  default     = null
}

variable "policy_uri" {
  description = "(optional) - *Early Access Property*. URI to web page providing client policy document."
  type        = string
  default     = null
}

variable "post_logout_redirect_uris" {
  description = "(optional) - List of URIs for redirection after logout"
  type        = set(string)
  default     = null
}

variable "profile" {
  description = "(optional) - Custom JSON that represents an OAuth application's profile"
  type        = string
  default     = null
}

variable "redirect_uris" {
  description = "(optional) - List of URIs for use in the redirect-based flow. This is required for all application types except service. Note: see okta_app_oauth_redirect_uri for appending to this list in a decentralized way."
  type        = set(string)
  default     = null
}

variable "response_types" {
  description = "(optional) - List of OAuth 2.0 response type strings."
  type        = set(string)
  default     = null
}

variable "status" {
  description = "(optional) - Status of application."
  type        = string
  default     = null
}

variable "token_endpoint_auth_method" {
  description = "(optional) - Requested authentication method for the token endpoint."
  type        = string
  default     = null
}

variable "tos_uri" {
  description = "(optional) - *Early Access Property*. URI to web page providing client tos (terms of service)."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The type of client application."
  type        = string
}

variable "jwks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      e   = string
      kid = string
      kty = string
      n   = string
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
resource "okta_oauth_app" "this" {
  auto_key_rotation          = var.auto_key_rotation
  auto_submit_toolbar        = var.auto_submit_toolbar
  client_basic_secret        = var.client_basic_secret
  client_id                  = var.client_id
  client_uri                 = var.client_uri
  consent_method             = var.consent_method
  custom_client_id           = var.custom_client_id
  grant_types                = var.grant_types
  groups                     = var.groups
  hide_ios                   = var.hide_ios
  hide_web                   = var.hide_web
  issuer_mode                = var.issuer_mode
  label                      = var.label
  login_uri                  = var.login_uri
  logo_uri                   = var.logo_uri
  omit_secret                = var.omit_secret
  policy_uri                 = var.policy_uri
  post_logout_redirect_uris  = var.post_logout_redirect_uris
  profile                    = var.profile
  redirect_uris              = var.redirect_uris
  response_types             = var.response_types
  status                     = var.status
  token_endpoint_auth_method = var.token_endpoint_auth_method
  tos_uri                    = var.tos_uri
  type                       = var.type

  dynamic "jwks" {
    for_each = var.jwks
    content {
      e   = jwks.value["e"]
      kid = jwks.value["kid"]
      kty = jwks.value["kty"]
      n   = jwks.value["n"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
      id       = users.value["id"]
      password = users.value["password"]
      username = users.value["username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = okta_oauth_app.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = okta_oauth_app.this.client_secret
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = okta_oauth_app.this.id
}

output "name" {
  description = "returns a string"
  value       = okta_oauth_app.this.name
}

output "sign_on_mode" {
  description = "returns a string"
  value       = okta_oauth_app.this.sign_on_mode
}

output "this" {
  value = okta_oauth_app.this
}
```

[top](#index)