# auth0_connection

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
module "auth0_connection" {
  source = "./modules/auth0/r/auth0_connection"

  # display_name - (optional) is a type of string
  display_name = null
  # enabled_clients - (optional) is a type of set of string
  enabled_clients = []
  # is_domain_connection - (optional) is a type of bool
  is_domain_connection = null
  # name - (required) is a type of string
  name = null
  # realms - (optional) is a type of list of string
  realms = []
  # strategy - (required) is a type of string
  strategy = null
  # strategy_version - (optional) is a type of string
  strategy_version = null

  options = [{
    adfs_server                    = null
    allowed_audiences              = []
    api_enable_users               = null
    app_domain                     = null
    app_id                         = null
    authorization_endpoint         = null
    brute_force_protection         = null
    client_id                      = null
    client_secret                  = null
    community_base_url             = null
    configuration                  = {}
    custom_scripts                 = {}
    debug                          = null
    digest_algorithm               = null
    disable_cache                  = null
    disable_signup                 = null
    discovery_url                  = null
    domain                         = null
    domain_aliases                 = []
    enabled_database_customization = null
    fields_map                     = {}
    from                           = null
    icon_url                       = null
    identity_api                   = null
    idp_initiated = [{
      client_authorize_query = null
      client_id              = null
      client_protocol        = null
    }]
    import_mode            = null
    ips                    = []
    issuer                 = null
    jwks_uri               = null
    key_id                 = null
    max_groups_to_retrieve = null
    messaging_service_sid  = null
    name                   = null
    password_complexity_options = [{
      min_length = null
    }]
    password_dictionary = [{
      dictionary = []
      enable     = null
    }]
    password_history = [{
      enable = null
      size   = null
    }]
    password_no_personal_info = [{
      enable = null
    }]
    password_policy     = null
    protocol_binding    = null
    requires_username   = null
    scopes              = []
    sign_in_endpoint    = null
    sign_out_endpoint   = null
    sign_saml_request   = null
    signature_algorithm = null
    signing_cert        = null
    strategy_version    = null
    subject             = null
    syntax              = null
    team_id             = null
    template            = null
    tenant_domain       = null
    token_endpoint      = null
    totp = [{
      length    = null
      time_step = null
    }]
    twilio_sid           = null
    twilio_token         = null
    type                 = null
    use_cert_auth        = null
    use_kerberos         = null
    use_wsfed            = null
    userinfo_endpoint    = null
    validation           = {}
    waad_common_endpoint = null
    waad_protocol        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional) - Name used in login screen"
  type        = string
  default     = null
}

variable "enabled_clients" {
  description = "(optional) - IDs of the clients for which the connection is enabled"
  type        = set(string)
  default     = null
}

variable "is_domain_connection" {
  description = "(optional) - Indicates whether or not the connection is domain level"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the connection"
  type        = string
}

variable "realms" {
  description = "(optional) - Defines the realms for which the connection will be used (i.e., email domains). If not specified, the connection name is added as the realm"
  type        = list(string)
  default     = null
}

variable "strategy" {
  description = "(required) - Type of the connection, which indicates the identity provider"
  type        = string
}

variable "strategy_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      adfs_server                    = string
      allowed_audiences              = set(string)
      api_enable_users               = bool
      app_domain                     = string
      app_id                         = string
      authorization_endpoint         = string
      brute_force_protection         = bool
      client_id                      = string
      client_secret                  = string
      community_base_url             = string
      configuration                  = map(string)
      custom_scripts                 = map(string)
      debug                          = bool
      digest_algorithm               = string
      disable_cache                  = bool
      disable_signup                 = bool
      discovery_url                  = string
      domain                         = string
      domain_aliases                 = set(string)
      enabled_database_customization = bool
      fields_map                     = map(string)
      from                           = string
      icon_url                       = string
      identity_api                   = string
      idp_initiated = list(object(
        {
          client_authorize_query = string
          client_id              = string
          client_protocol        = string
        }
      ))
      import_mode            = bool
      ips                    = set(string)
      issuer                 = string
      jwks_uri               = string
      key_id                 = string
      max_groups_to_retrieve = string
      messaging_service_sid  = string
      name                   = string
      password_complexity_options = list(object(
        {
          min_length = number
        }
      ))
      password_dictionary = list(object(
        {
          dictionary = set(string)
          enable     = bool
        }
      ))
      password_history = list(object(
        {
          enable = bool
          size   = number
        }
      ))
      password_no_personal_info = list(object(
        {
          enable = bool
        }
      ))
      password_policy     = string
      protocol_binding    = string
      requires_username   = bool
      scopes              = set(string)
      sign_in_endpoint    = string
      sign_out_endpoint   = string
      sign_saml_request   = bool
      signature_algorithm = string
      signing_cert        = string
      strategy_version    = number
      subject             = string
      syntax              = string
      team_id             = string
      template            = string
      tenant_domain       = string
      token_endpoint      = string
      totp = list(object(
        {
          length    = number
          time_step = number
        }
      ))
      twilio_sid           = string
      twilio_token         = string
      type                 = string
      use_cert_auth        = bool
      use_kerberos         = bool
      use_wsfed            = bool
      userinfo_endpoint    = string
      validation           = map(string)
      waad_common_endpoint = bool
      waad_protocol        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "auth0_connection" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # enabled_clients - (optional) is a type of set of string
  enabled_clients = var.enabled_clients
  # is_domain_connection - (optional) is a type of bool
  is_domain_connection = var.is_domain_connection
  # name - (required) is a type of string
  name = var.name
  # realms - (optional) is a type of list of string
  realms = var.realms
  # strategy - (required) is a type of string
  strategy = var.strategy
  # strategy_version - (optional) is a type of string
  strategy_version = var.strategy_version

  dynamic "options" {
    for_each = var.options
    content {
      # adfs_server - (optional) is a type of string
      adfs_server = options.value["adfs_server"]
      # allowed_audiences - (optional) is a type of set of string
      allowed_audiences = options.value["allowed_audiences"]
      # api_enable_users - (optional) is a type of bool
      api_enable_users = options.value["api_enable_users"]
      # app_domain - (optional) is a type of string
      app_domain = options.value["app_domain"]
      # app_id - (optional) is a type of string
      app_id = options.value["app_id"]
      # authorization_endpoint - (optional) is a type of string
      authorization_endpoint = options.value["authorization_endpoint"]
      # brute_force_protection - (optional) is a type of bool
      brute_force_protection = options.value["brute_force_protection"]
      # client_id - (optional) is a type of string
      client_id = options.value["client_id"]
      # client_secret - (optional) is a type of string
      client_secret = options.value["client_secret"]
      # community_base_url - (optional) is a type of string
      community_base_url = options.value["community_base_url"]
      # configuration - (optional) is a type of map of string
      configuration = options.value["configuration"]
      # custom_scripts - (optional) is a type of map of string
      custom_scripts = options.value["custom_scripts"]
      # debug - (optional) is a type of bool
      debug = options.value["debug"]
      # digest_algorithm - (optional) is a type of string
      digest_algorithm = options.value["digest_algorithm"]
      # disable_cache - (optional) is a type of bool
      disable_cache = options.value["disable_cache"]
      # disable_signup - (optional) is a type of bool
      disable_signup = options.value["disable_signup"]
      # discovery_url - (optional) is a type of string
      discovery_url = options.value["discovery_url"]
      # domain - (optional) is a type of string
      domain = options.value["domain"]
      # domain_aliases - (optional) is a type of set of string
      domain_aliases = options.value["domain_aliases"]
      # enabled_database_customization - (optional) is a type of bool
      enabled_database_customization = options.value["enabled_database_customization"]
      # fields_map - (optional) is a type of map of string
      fields_map = options.value["fields_map"]
      # from - (optional) is a type of string
      from = options.value["from"]
      # icon_url - (optional) is a type of string
      icon_url = options.value["icon_url"]
      # identity_api - (optional) is a type of string
      identity_api = options.value["identity_api"]
      # import_mode - (optional) is a type of bool
      import_mode = options.value["import_mode"]
      # ips - (optional) is a type of set of string
      ips = options.value["ips"]
      # issuer - (optional) is a type of string
      issuer = options.value["issuer"]
      # jwks_uri - (optional) is a type of string
      jwks_uri = options.value["jwks_uri"]
      # key_id - (optional) is a type of string
      key_id = options.value["key_id"]
      # max_groups_to_retrieve - (optional) is a type of string
      max_groups_to_retrieve = options.value["max_groups_to_retrieve"]
      # messaging_service_sid - (optional) is a type of string
      messaging_service_sid = options.value["messaging_service_sid"]
      # name - (optional) is a type of string
      name = options.value["name"]
      # password_policy - (optional) is a type of string
      password_policy = options.value["password_policy"]
      # protocol_binding - (optional) is a type of string
      protocol_binding = options.value["protocol_binding"]
      # requires_username - (optional) is a type of bool
      requires_username = options.value["requires_username"]
      # scopes - (optional) is a type of set of string
      scopes = options.value["scopes"]
      # sign_in_endpoint - (optional) is a type of string
      sign_in_endpoint = options.value["sign_in_endpoint"]
      # sign_out_endpoint - (optional) is a type of string
      sign_out_endpoint = options.value["sign_out_endpoint"]
      # sign_saml_request - (optional) is a type of bool
      sign_saml_request = options.value["sign_saml_request"]
      # signature_algorithm - (optional) is a type of string
      signature_algorithm = options.value["signature_algorithm"]
      # signing_cert - (optional) is a type of string
      signing_cert = options.value["signing_cert"]
      # strategy_version - (optional) is a type of number
      strategy_version = options.value["strategy_version"]
      # subject - (optional) is a type of string
      subject = options.value["subject"]
      # syntax - (optional) is a type of string
      syntax = options.value["syntax"]
      # team_id - (optional) is a type of string
      team_id = options.value["team_id"]
      # template - (optional) is a type of string
      template = options.value["template"]
      # tenant_domain - (optional) is a type of string
      tenant_domain = options.value["tenant_domain"]
      # token_endpoint - (optional) is a type of string
      token_endpoint = options.value["token_endpoint"]
      # twilio_sid - (optional) is a type of string
      twilio_sid = options.value["twilio_sid"]
      # twilio_token - (optional) is a type of string
      twilio_token = options.value["twilio_token"]
      # type - (optional) is a type of string
      type = options.value["type"]
      # use_cert_auth - (optional) is a type of bool
      use_cert_auth = options.value["use_cert_auth"]
      # use_kerberos - (optional) is a type of bool
      use_kerberos = options.value["use_kerberos"]
      # use_wsfed - (optional) is a type of bool
      use_wsfed = options.value["use_wsfed"]
      # userinfo_endpoint - (optional) is a type of string
      userinfo_endpoint = options.value["userinfo_endpoint"]
      # validation - (optional) is a type of map of string
      validation = options.value["validation"]
      # waad_common_endpoint - (optional) is a type of bool
      waad_common_endpoint = options.value["waad_common_endpoint"]
      # waad_protocol - (optional) is a type of string
      waad_protocol = options.value["waad_protocol"]

      dynamic "idp_initiated" {
        for_each = options.value.idp_initiated
        content {
          # client_authorize_query - (optional) is a type of string
          client_authorize_query = idp_initiated.value["client_authorize_query"]
          # client_id - (optional) is a type of string
          client_id = idp_initiated.value["client_id"]
          # client_protocol - (optional) is a type of string
          client_protocol = idp_initiated.value["client_protocol"]
        }
      }

      dynamic "password_complexity_options" {
        for_each = options.value.password_complexity_options
        content {
          # min_length - (optional) is a type of number
          min_length = password_complexity_options.value["min_length"]
        }
      }

      dynamic "password_dictionary" {
        for_each = options.value.password_dictionary
        content {
          # dictionary - (optional) is a type of set of string
          dictionary = password_dictionary.value["dictionary"]
          # enable - (optional) is a type of bool
          enable = password_dictionary.value["enable"]
        }
      }

      dynamic "password_history" {
        for_each = options.value.password_history
        content {
          # enable - (optional) is a type of bool
          enable = password_history.value["enable"]
          # size - (optional) is a type of number
          size = password_history.value["size"]
        }
      }

      dynamic "password_no_personal_info" {
        for_each = options.value.password_no_personal_info
        content {
          # enable - (optional) is a type of bool
          enable = password_no_personal_info.value["enable"]
        }
      }

      dynamic "totp" {
        for_each = options.value.totp
        content {
          # length - (optional) is a type of number
          length = totp.value["length"]
          # time_step - (optional) is a type of number
          time_step = totp.value["time_step"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "enabled_clients" {
  description = "returns a set of string"
  value       = auth0_connection.this.enabled_clients
}

output "id" {
  description = "returns a string"
  value       = auth0_connection.this.id
}

output "is_domain_connection" {
  description = "returns a bool"
  value       = auth0_connection.this.is_domain_connection
}

output "realms" {
  description = "returns a list of string"
  value       = auth0_connection.this.realms
}

output "strategy_version" {
  description = "returns a string"
  value       = auth0_connection.this.strategy_version
}

output "this" {
  value = auth0_connection.this
}
```

[top](#index)