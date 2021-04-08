# auth0_client

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
module "auth0_client" {
  source = "./modules/auth0/r/auth0_client"

  # allowed_logout_urls - (optional) is a type of list of string
  allowed_logout_urls = []
  # allowed_origins - (optional) is a type of list of string
  allowed_origins = []
  # app_type - (optional) is a type of string
  app_type = null
  # callbacks - (optional) is a type of list of string
  callbacks = []
  # client_metadata - (optional) is a type of map of string
  client_metadata = {}
  # client_secret_rotation_trigger - (optional) is a type of map of string
  client_secret_rotation_trigger = {}
  # cross_origin_auth - (optional) is a type of bool
  cross_origin_auth = null
  # cross_origin_loc - (optional) is a type of string
  cross_origin_loc = null
  # custom_login_page - (optional) is a type of string
  custom_login_page = null
  # custom_login_page_on - (optional) is a type of bool
  custom_login_page_on = null
  # custom_login_page_preview - (optional) is a type of string
  custom_login_page_preview = null
  # description - (optional) is a type of string
  description = null
  # encryption_key - (optional) is a type of map of string
  encryption_key = {}
  # form_template - (optional) is a type of string
  form_template = null
  # grant_types - (optional) is a type of list of string
  grant_types = []
  # initiate_login_uri - (optional) is a type of string
  initiate_login_uri = null
  # is_first_party - (optional) is a type of bool
  is_first_party = null
  # is_token_endpoint_ip_header_trusted - (optional) is a type of bool
  is_token_endpoint_ip_header_trusted = null
  # logo_uri - (optional) is a type of string
  logo_uri = null
  # name - (required) is a type of string
  name = null
  # oidc_conformant - (optional) is a type of bool
  oidc_conformant = null
  # sso - (optional) is a type of bool
  sso = null
  # sso_disabled - (optional) is a type of bool
  sso_disabled = null
  # token_endpoint_auth_method - (optional) is a type of string
  token_endpoint_auth_method = null
  # web_origins - (optional) is a type of list of string
  web_origins = []

  addons = [{
    aws                    = {}
    azure_blob             = {}
    azure_sb               = {}
    box                    = {}
    cloudbees              = {}
    concur                 = {}
    dropbox                = {}
    echosign               = {}
    egnyte                 = {}
    firebase               = {}
    layer                  = {}
    mscrm                  = {}
    newrelic               = {}
    office365              = {}
    rms                    = {}
    salesforce             = {}
    salesforce_api         = {}
    salesforce_sandbox_api = {}
    samlp = [{
      audience                           = null
      authn_context_class_ref            = null
      binding                            = null
      create_upn_claim                   = null
      destination                        = null
      digest_algorithm                   = null
      include_attribute_name_format      = null
      lifetime_in_seconds                = null
      logout                             = {}
      map_identities                     = null
      map_unknown_claims_as_is           = null
      mappings                           = {}
      name_identifier_format             = null
      name_identifier_probes             = []
      passthrough_claims_with_no_mapping = null
      recipient                          = null
      sign_response                      = null
      signature_algorithm                = null
      typed_attributes                   = null
    }]
    sap_api    = {}
    sentry     = {}
    sharepoint = {}
    slack      = {}
    springcm   = {}
    wams       = {}
    wsfed      = {}
    zendesk    = {}
    zoom       = {}
  }]

  jwt_configuration = [{
    alg                 = null
    lifetime_in_seconds = null
    scopes              = {}
    secret_encoded      = null
  }]

  mobile = [{
    android = [{
      app_package_name         = null
      sha256_cert_fingerprints = []
    }]
    ios = [{
      app_bundle_identifier = null
      team_id               = null
    }]
  }]

  refresh_token = [{
    expiration_type = null
    leeway          = null
    rotation_type   = null
    token_lifetime  = null
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

variable "allowed_origins" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "app_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "callbacks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "client_metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "client_secret_rotation_trigger" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cross_origin_auth" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cross_origin_loc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_login_page" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_login_page_on" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "custom_login_page_preview" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption_key" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "form_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "grant_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "initiate_login_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_first_party" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_token_endpoint_ip_header_trusted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "logo_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "oidc_conformant" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sso" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sso_disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "token_endpoint_auth_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_origins" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "addons" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aws                    = map(string)
      azure_blob             = map(string)
      azure_sb               = map(string)
      box                    = map(string)
      cloudbees              = map(string)
      concur                 = map(string)
      dropbox                = map(string)
      echosign               = map(string)
      egnyte                 = map(string)
      firebase               = map(string)
      layer                  = map(string)
      mscrm                  = map(string)
      newrelic               = map(string)
      office365              = map(string)
      rms                    = map(string)
      salesforce             = map(string)
      salesforce_api         = map(string)
      salesforce_sandbox_api = map(string)
      samlp = list(object(
        {
          audience                           = string
          authn_context_class_ref            = string
          binding                            = string
          create_upn_claim                   = bool
          destination                        = string
          digest_algorithm                   = string
          include_attribute_name_format      = bool
          lifetime_in_seconds                = number
          logout                             = map(string)
          map_identities                     = bool
          map_unknown_claims_as_is           = bool
          mappings                           = map(string)
          name_identifier_format             = string
          name_identifier_probes             = list(string)
          passthrough_claims_with_no_mapping = bool
          recipient                          = string
          sign_response                      = bool
          signature_algorithm                = string
          typed_attributes                   = bool
        }
      ))
      sap_api    = map(string)
      sentry     = map(string)
      sharepoint = map(string)
      slack      = map(string)
      springcm   = map(string)
      wams       = map(string)
      wsfed      = map(string)
      zendesk    = map(string)
      zoom       = map(string)
    }
  ))
  default = []
}

variable "jwt_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      alg                 = string
      lifetime_in_seconds = number
      scopes              = map(string)
      secret_encoded      = bool
    }
  ))
  default = []
}

variable "mobile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      android = list(object(
        {
          app_package_name         = string
          sha256_cert_fingerprints = list(string)
        }
      ))
      ios = list(object(
        {
          app_bundle_identifier = string
          team_id               = string
        }
      ))
    }
  ))
  default = []
}

variable "refresh_token" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      expiration_type = string
      leeway          = number
      rotation_type   = string
      token_lifetime  = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "auth0_client" "this" {
  # allowed_logout_urls - (optional) is a type of list of string
  allowed_logout_urls = var.allowed_logout_urls
  # allowed_origins - (optional) is a type of list of string
  allowed_origins = var.allowed_origins
  # app_type - (optional) is a type of string
  app_type = var.app_type
  # callbacks - (optional) is a type of list of string
  callbacks = var.callbacks
  # client_metadata - (optional) is a type of map of string
  client_metadata = var.client_metadata
  # client_secret_rotation_trigger - (optional) is a type of map of string
  client_secret_rotation_trigger = var.client_secret_rotation_trigger
  # cross_origin_auth - (optional) is a type of bool
  cross_origin_auth = var.cross_origin_auth
  # cross_origin_loc - (optional) is a type of string
  cross_origin_loc = var.cross_origin_loc
  # custom_login_page - (optional) is a type of string
  custom_login_page = var.custom_login_page
  # custom_login_page_on - (optional) is a type of bool
  custom_login_page_on = var.custom_login_page_on
  # custom_login_page_preview - (optional) is a type of string
  custom_login_page_preview = var.custom_login_page_preview
  # description - (optional) is a type of string
  description = var.description
  # encryption_key - (optional) is a type of map of string
  encryption_key = var.encryption_key
  # form_template - (optional) is a type of string
  form_template = var.form_template
  # grant_types - (optional) is a type of list of string
  grant_types = var.grant_types
  # initiate_login_uri - (optional) is a type of string
  initiate_login_uri = var.initiate_login_uri
  # is_first_party - (optional) is a type of bool
  is_first_party = var.is_first_party
  # is_token_endpoint_ip_header_trusted - (optional) is a type of bool
  is_token_endpoint_ip_header_trusted = var.is_token_endpoint_ip_header_trusted
  # logo_uri - (optional) is a type of string
  logo_uri = var.logo_uri
  # name - (required) is a type of string
  name = var.name
  # oidc_conformant - (optional) is a type of bool
  oidc_conformant = var.oidc_conformant
  # sso - (optional) is a type of bool
  sso = var.sso
  # sso_disabled - (optional) is a type of bool
  sso_disabled = var.sso_disabled
  # token_endpoint_auth_method - (optional) is a type of string
  token_endpoint_auth_method = var.token_endpoint_auth_method
  # web_origins - (optional) is a type of list of string
  web_origins = var.web_origins

  dynamic "addons" {
    for_each = var.addons
    content {
      # aws - (optional) is a type of map of string
      aws = addons.value["aws"]
      # azure_blob - (optional) is a type of map of string
      azure_blob = addons.value["azure_blob"]
      # azure_sb - (optional) is a type of map of string
      azure_sb = addons.value["azure_sb"]
      # box - (optional) is a type of map of string
      box = addons.value["box"]
      # cloudbees - (optional) is a type of map of string
      cloudbees = addons.value["cloudbees"]
      # concur - (optional) is a type of map of string
      concur = addons.value["concur"]
      # dropbox - (optional) is a type of map of string
      dropbox = addons.value["dropbox"]
      # echosign - (optional) is a type of map of string
      echosign = addons.value["echosign"]
      # egnyte - (optional) is a type of map of string
      egnyte = addons.value["egnyte"]
      # firebase - (optional) is a type of map of string
      firebase = addons.value["firebase"]
      # layer - (optional) is a type of map of string
      layer = addons.value["layer"]
      # mscrm - (optional) is a type of map of string
      mscrm = addons.value["mscrm"]
      # newrelic - (optional) is a type of map of string
      newrelic = addons.value["newrelic"]
      # office365 - (optional) is a type of map of string
      office365 = addons.value["office365"]
      # rms - (optional) is a type of map of string
      rms = addons.value["rms"]
      # salesforce - (optional) is a type of map of string
      salesforce = addons.value["salesforce"]
      # salesforce_api - (optional) is a type of map of string
      salesforce_api = addons.value["salesforce_api"]
      # salesforce_sandbox_api - (optional) is a type of map of string
      salesforce_sandbox_api = addons.value["salesforce_sandbox_api"]
      # sap_api - (optional) is a type of map of string
      sap_api = addons.value["sap_api"]
      # sentry - (optional) is a type of map of string
      sentry = addons.value["sentry"]
      # sharepoint - (optional) is a type of map of string
      sharepoint = addons.value["sharepoint"]
      # slack - (optional) is a type of map of string
      slack = addons.value["slack"]
      # springcm - (optional) is a type of map of string
      springcm = addons.value["springcm"]
      # wams - (optional) is a type of map of string
      wams = addons.value["wams"]
      # wsfed - (optional) is a type of map of string
      wsfed = addons.value["wsfed"]
      # zendesk - (optional) is a type of map of string
      zendesk = addons.value["zendesk"]
      # zoom - (optional) is a type of map of string
      zoom = addons.value["zoom"]

      dynamic "samlp" {
        for_each = addons.value.samlp
        content {
          # audience - (optional) is a type of string
          audience = samlp.value["audience"]
          # authn_context_class_ref - (optional) is a type of string
          authn_context_class_ref = samlp.value["authn_context_class_ref"]
          # binding - (optional) is a type of string
          binding = samlp.value["binding"]
          # create_upn_claim - (optional) is a type of bool
          create_upn_claim = samlp.value["create_upn_claim"]
          # destination - (optional) is a type of string
          destination = samlp.value["destination"]
          # digest_algorithm - (optional) is a type of string
          digest_algorithm = samlp.value["digest_algorithm"]
          # include_attribute_name_format - (optional) is a type of bool
          include_attribute_name_format = samlp.value["include_attribute_name_format"]
          # lifetime_in_seconds - (optional) is a type of number
          lifetime_in_seconds = samlp.value["lifetime_in_seconds"]
          # logout - (optional) is a type of map of string
          logout = samlp.value["logout"]
          # map_identities - (optional) is a type of bool
          map_identities = samlp.value["map_identities"]
          # map_unknown_claims_as_is - (optional) is a type of bool
          map_unknown_claims_as_is = samlp.value["map_unknown_claims_as_is"]
          # mappings - (optional) is a type of map of string
          mappings = samlp.value["mappings"]
          # name_identifier_format - (optional) is a type of string
          name_identifier_format = samlp.value["name_identifier_format"]
          # name_identifier_probes - (optional) is a type of list of string
          name_identifier_probes = samlp.value["name_identifier_probes"]
          # passthrough_claims_with_no_mapping - (optional) is a type of bool
          passthrough_claims_with_no_mapping = samlp.value["passthrough_claims_with_no_mapping"]
          # recipient - (optional) is a type of string
          recipient = samlp.value["recipient"]
          # sign_response - (optional) is a type of bool
          sign_response = samlp.value["sign_response"]
          # signature_algorithm - (optional) is a type of string
          signature_algorithm = samlp.value["signature_algorithm"]
          # typed_attributes - (optional) is a type of bool
          typed_attributes = samlp.value["typed_attributes"]
        }
      }

    }
  }

  dynamic "jwt_configuration" {
    for_each = var.jwt_configuration
    content {
      # alg - (optional) is a type of string
      alg = jwt_configuration.value["alg"]
      # lifetime_in_seconds - (optional) is a type of number
      lifetime_in_seconds = jwt_configuration.value["lifetime_in_seconds"]
      # scopes - (optional) is a type of map of string
      scopes = jwt_configuration.value["scopes"]
      # secret_encoded - (optional) is a type of bool
      secret_encoded = jwt_configuration.value["secret_encoded"]
    }
  }

  dynamic "mobile" {
    for_each = var.mobile
    content {

      dynamic "android" {
        for_each = mobile.value.android
        content {
          # app_package_name - (optional) is a type of string
          app_package_name = android.value["app_package_name"]
          # sha256_cert_fingerprints - (optional) is a type of list of string
          sha256_cert_fingerprints = android.value["sha256_cert_fingerprints"]
        }
      }

      dynamic "ios" {
        for_each = mobile.value.ios
        content {
          # app_bundle_identifier - (optional) is a type of string
          app_bundle_identifier = ios.value["app_bundle_identifier"]
          # team_id - (optional) is a type of string
          team_id = ios.value["team_id"]
        }
      }

    }
  }

  dynamic "refresh_token" {
    for_each = var.refresh_token
    content {
      # expiration_type - (required) is a type of string
      expiration_type = refresh_token.value["expiration_type"]
      # leeway - (optional) is a type of number
      leeway = refresh_token.value["leeway"]
      # rotation_type - (required) is a type of string
      rotation_type = refresh_token.value["rotation_type"]
      # token_lifetime - (optional) is a type of number
      token_lifetime = refresh_token.value["token_lifetime"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = auth0_client.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = auth0_client.this.client_secret
  sensitive   = true
}

output "custom_login_page_on" {
  description = "returns a bool"
  value       = auth0_client.this.custom_login_page_on
}

output "grant_types" {
  description = "returns a list of string"
  value       = auth0_client.this.grant_types
}

output "id" {
  description = "returns a string"
  value       = auth0_client.this.id
}

output "is_first_party" {
  description = "returns a bool"
  value       = auth0_client.this.is_first_party
}

output "is_token_endpoint_ip_header_trusted" {
  description = "returns a bool"
  value       = auth0_client.this.is_token_endpoint_ip_header_trusted
}

output "oidc_conformant" {
  description = "returns a bool"
  value       = auth0_client.this.oidc_conformant
}

output "token_endpoint_auth_method" {
  description = "returns a string"
  value       = auth0_client.this.token_endpoint_auth_method
}

output "this" {
  value = auth0_client.this
}
```

[top](#index)