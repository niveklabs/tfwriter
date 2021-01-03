# bigip_ltm_profile_client_ssl

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_profile_client_ssl" {
  source = "./modules/bigip/r/bigip_ltm_profile_client_ssl"

  # alert_timeout - (optional) is a type of string
  alert_timeout = null
  # allow_non_ssl - (optional) is a type of string
  allow_non_ssl = null
  # authenticate - (optional) is a type of string
  authenticate = null
  # authenticate_depth - (optional) is a type of number
  authenticate_depth = null
  # ca_file - (optional) is a type of string
  ca_file = null
  # cache_size - (optional) is a type of number
  cache_size = null
  # cache_timeout - (optional) is a type of number
  cache_timeout = null
  # cert - (optional) is a type of string
  cert = null
  # cert_extension_includes - (optional) is a type of set of string
  cert_extension_includes = []
  # cert_life_span - (optional) is a type of number
  cert_life_span = null
  # cert_lookup_by_ipaddr_port - (optional) is a type of string
  cert_lookup_by_ipaddr_port = null
  # chain - (optional) is a type of string
  chain = null
  # ciphers - (optional) is a type of string
  ciphers = null
  # client_cert_ca - (optional) is a type of string
  client_cert_ca = null
  # crl_file - (optional) is a type of string
  crl_file = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # forward_proxy_bypass_default_action - (optional) is a type of string
  forward_proxy_bypass_default_action = null
  # full_path - (optional) is a type of string
  full_path = null
  # generation - (optional) is a type of number
  generation = null
  # generic_alert - (optional) is a type of string
  generic_alert = null
  # handshake_timeout - (optional) is a type of string
  handshake_timeout = null
  # inherit_cert_keychain - (optional) is a type of string
  inherit_cert_keychain = null
  # key - (optional) is a type of string
  key = null
  # mod_ssl_methods - (optional) is a type of string
  mod_ssl_methods = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
  # passphrase - (optional) is a type of string
  passphrase = null
  # peer_cert_mode - (optional) is a type of string
  peer_cert_mode = null
  # proxy_ca_cert - (optional) is a type of string
  proxy_ca_cert = null
  # proxy_ca_key - (optional) is a type of string
  proxy_ca_key = null
  # proxy_ca_passphrase - (optional) is a type of string
  proxy_ca_passphrase = null
  # proxy_ssl - (optional) is a type of string
  proxy_ssl = null
  # proxy_ssl_passthrough - (optional) is a type of string
  proxy_ssl_passthrough = null
  # renegotiate_period - (optional) is a type of string
  renegotiate_period = null
  # renegotiate_size - (optional) is a type of string
  renegotiate_size = null
  # renegotiation - (optional) is a type of string
  renegotiation = null
  # retain_certificate - (optional) is a type of string
  retain_certificate = null
  # secure_renegotiation - (optional) is a type of string
  secure_renegotiation = null
  # server_name - (optional) is a type of string
  server_name = null
  # session_mirroring - (optional) is a type of string
  session_mirroring = null
  # session_ticket - (optional) is a type of string
  session_ticket = null
  # sni_default - (optional) is a type of string
  sni_default = null
  # sni_require - (optional) is a type of string
  sni_require = null
  # ssl_forward_proxy - (optional) is a type of string
  ssl_forward_proxy = null
  # ssl_forward_proxy_bypass - (optional) is a type of string
  ssl_forward_proxy_bypass = null
  # ssl_sign_hash - (optional) is a type of string
  ssl_sign_hash = null
  # strict_resume - (optional) is a type of string
  strict_resume = null
  # tm_options - (optional) is a type of set of string
  tm_options = []
  # unclean_shutdown - (optional) is a type of string
  unclean_shutdown = null

  cert_key_chain = [{
    cert       = null
    chain      = null
    key        = null
    name       = null
    passphrase = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alert_timeout" {
  description = "(optional) - Alert time out"
  type        = string
  default     = null
}

variable "allow_non_ssl" {
  description = "(optional) - Allow non ssl"
  type        = string
  default     = null
}

variable "authenticate" {
  description = "(optional) - Server authentication once / always (default is once)."
  type        = string
  default     = null
}

variable "authenticate_depth" {
  description = "(optional) - Client certificate chain traversal depth.  Default 9."
  type        = number
  default     = null
}

variable "ca_file" {
  description = "(optional) - Client certificate file path.  Default None."
  type        = string
  default     = null
}

variable "cache_size" {
  description = "(optional) - Cache size (sessions)."
  type        = number
  default     = null
}

variable "cache_timeout" {
  description = "(optional) - Cache time out"
  type        = number
  default     = null
}

variable "cert" {
  description = "(optional) - Name of the server certificate."
  type        = string
  default     = null
}

variable "cert_extension_includes" {
  description = "(optional) - Cert extension includes for ssl forward proxy"
  type        = set(string)
  default     = null
}

variable "cert_life_span" {
  description = "(optional) - Life span of the certificate in days for ssl forward proxy"
  type        = number
  default     = null
}

variable "cert_lookup_by_ipaddr_port" {
  description = "(optional) - Cert lookup by ip address and port enabled / disabled"
  type        = string
  default     = null
}

variable "chain" {
  description = "(optional) - Client certificate chain name."
  type        = string
  default     = null
}

variable "ciphers" {
  description = "(optional) - BigIP Cipher string."
  type        = string
  default     = null
}

variable "client_cert_ca" {
  description = "(optional) - client certificate name"
  type        = string
  default     = null
}

variable "crl_file" {
  description = "(optional) - Certificate revocation file name"
  type        = string
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Profile name that this profile defaults from."
  type        = string
  default     = null
}

variable "forward_proxy_bypass_default_action" {
  description = "(optional) - Forward proxy bypass default action. (enabled / disabled)"
  type        = string
  default     = null
}

variable "full_path" {
  description = "(optional) - full path of the profile"
  type        = string
  default     = null
}

variable "generation" {
  description = "(optional) - generation"
  type        = number
  default     = null
}

variable "generic_alert" {
  description = "(optional) - Generic alerts enabled / disabled."
  type        = string
  default     = null
}

variable "handshake_timeout" {
  description = "(optional) - Handshake time out (seconds)"
  type        = string
  default     = null
}

variable "inherit_cert_keychain" {
  description = "(optional) - Inherit cert key chain"
  type        = string
  default     = null
}

variable "key" {
  description = "(optional) - Name of the Server SSL profile key"
  type        = string
  default     = null
}

variable "mod_ssl_methods" {
  description = "(optional) - ModSSL Methods enabled / disabled.  Default is disabled."
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional) - ModSSL Methods enabled / disabled.  Default is disabled."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the Ssl Profile"
  type        = string
}

variable "partition" {
  description = "(optional) - name of partition"
  type        = string
  default     = null
}

variable "passphrase" {
  description = "(optional) - Client Certificate Constrained Delegation CA passphrase"
  type        = string
  default     = null
}

variable "peer_cert_mode" {
  description = "(optional) - Peer Cert Mode"
  type        = string
  default     = null
}

variable "proxy_ca_cert" {
  description = "(optional) - Proxy CA Cert"
  type        = string
  default     = null
}

variable "proxy_ca_key" {
  description = "(optional) - Proxy CA Key"
  type        = string
  default     = null
}

variable "proxy_ca_passphrase" {
  description = "(optional) - Proxy CA Passphrase"
  type        = string
  default     = null
}

variable "proxy_ssl" {
  description = "(optional) - Proxy SSL enabled / disabled.  Default is disabled."
  type        = string
  default     = null
}

variable "proxy_ssl_passthrough" {
  description = "(optional) - Proxy SSL passthrough enabled / disabled.  Default is disabled."
  type        = string
  default     = null
}

variable "renegotiate_period" {
  description = "(optional) - Renogotiate Period (seconds)"
  type        = string
  default     = null
}

variable "renegotiate_size" {
  description = "(optional) - Renogotiate Size"
  type        = string
  default     = null
}

variable "renegotiation" {
  description = "(optional) - Renegotiation (enabled / disabled)"
  type        = string
  default     = null
}

variable "retain_certificate" {
  description = "(optional) - Retain certificate."
  type        = string
  default     = null
}

variable "secure_renegotiation" {
  description = "(optional) - Secure reneogotiaton (request / require / require-strict)."
  type        = string
  default     = null
}

variable "server_name" {
  description = "(optional) - Server name"
  type        = string
  default     = null
}

variable "session_mirroring" {
  description = "(optional) - Session Mirroring (enabled / disabled)"
  type        = string
  default     = null
}

variable "session_ticket" {
  description = "(optional) - Session Ticket (enabled / disabled)"
  type        = string
  default     = null
}

variable "sni_default" {
  description = "(optional) - SNI Default (true / false)"
  type        = string
  default     = null
}

variable "sni_require" {
  description = "(optional) - SNI Require (true / false)"
  type        = string
  default     = null
}

variable "ssl_forward_proxy" {
  description = "(optional) - SSL forward Proxy (enabled / disabled)"
  type        = string
  default     = null
}

variable "ssl_forward_proxy_bypass" {
  description = "(optional) - SSL forward Proxy Bypass (enabled / disabled)"
  type        = string
  default     = null
}

variable "ssl_sign_hash" {
  description = "(optional) - SSL sign hash (any, sha1, sha256, sha384)"
  type        = string
  default     = null
}

variable "strict_resume" {
  description = "(optional) - Strict Resume (enabled / disabled)"
  type        = string
  default     = null
}

variable "tm_options" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "unclean_shutdown" {
  description = "(optional) - Unclean Shutdown (enabled / disabled)"
  type        = string
  default     = null
}

variable "cert_key_chain" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cert       = string
      chain      = string
      key        = string
      name       = string
      passphrase = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_client_ssl" "this" {
  alert_timeout                       = var.alert_timeout
  allow_non_ssl                       = var.allow_non_ssl
  authenticate                        = var.authenticate
  authenticate_depth                  = var.authenticate_depth
  ca_file                             = var.ca_file
  cache_size                          = var.cache_size
  cache_timeout                       = var.cache_timeout
  cert                                = var.cert
  cert_extension_includes             = var.cert_extension_includes
  cert_life_span                      = var.cert_life_span
  cert_lookup_by_ipaddr_port          = var.cert_lookup_by_ipaddr_port
  chain                               = var.chain
  ciphers                             = var.ciphers
  client_cert_ca                      = var.client_cert_ca
  crl_file                            = var.crl_file
  defaults_from                       = var.defaults_from
  forward_proxy_bypass_default_action = var.forward_proxy_bypass_default_action
  full_path                           = var.full_path
  generation                          = var.generation
  generic_alert                       = var.generic_alert
  handshake_timeout                   = var.handshake_timeout
  inherit_cert_keychain               = var.inherit_cert_keychain
  key                                 = var.key
  mod_ssl_methods                     = var.mod_ssl_methods
  mode                                = var.mode
  name                                = var.name
  partition                           = var.partition
  passphrase                          = var.passphrase
  peer_cert_mode                      = var.peer_cert_mode
  proxy_ca_cert                       = var.proxy_ca_cert
  proxy_ca_key                        = var.proxy_ca_key
  proxy_ca_passphrase                 = var.proxy_ca_passphrase
  proxy_ssl                           = var.proxy_ssl
  proxy_ssl_passthrough               = var.proxy_ssl_passthrough
  renegotiate_period                  = var.renegotiate_period
  renegotiate_size                    = var.renegotiate_size
  renegotiation                       = var.renegotiation
  retain_certificate                  = var.retain_certificate
  secure_renegotiation                = var.secure_renegotiation
  server_name                         = var.server_name
  session_mirroring                   = var.session_mirroring
  session_ticket                      = var.session_ticket
  sni_default                         = var.sni_default
  sni_require                         = var.sni_require
  ssl_forward_proxy                   = var.ssl_forward_proxy
  ssl_forward_proxy_bypass            = var.ssl_forward_proxy_bypass
  ssl_sign_hash                       = var.ssl_sign_hash
  strict_resume                       = var.strict_resume
  tm_options                          = var.tm_options
  unclean_shutdown                    = var.unclean_shutdown

  dynamic "cert_key_chain" {
    for_each = var.cert_key_chain
    content {
      cert       = cert_key_chain.value["cert"]
      chain      = cert_key_chain.value["chain"]
      key        = cert_key_chain.value["key"]
      name       = cert_key_chain.value["name"]
      passphrase = cert_key_chain.value["passphrase"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alert_timeout" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.alert_timeout
}

output "allow_non_ssl" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.allow_non_ssl
}

output "authenticate" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.authenticate
}

output "authenticate_depth" {
  description = "returns a number"
  value       = bigip_ltm_profile_client_ssl.this.authenticate_depth
}

output "ca_file" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.ca_file
}

output "cache_size" {
  description = "returns a number"
  value       = bigip_ltm_profile_client_ssl.this.cache_size
}

output "cache_timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_client_ssl.this.cache_timeout
}

output "cert" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.cert
}

output "cert_extension_includes" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_client_ssl.this.cert_extension_includes
}

output "cert_life_span" {
  description = "returns a number"
  value       = bigip_ltm_profile_client_ssl.this.cert_life_span
}

output "cert_lookup_by_ipaddr_port" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.cert_lookup_by_ipaddr_port
}

output "chain" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.chain
}

output "ciphers" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.ciphers
}

output "client_cert_ca" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.client_cert_ca
}

output "crl_file" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.crl_file
}

output "forward_proxy_bypass_default_action" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.forward_proxy_bypass_default_action
}

output "full_path" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.full_path
}

output "generation" {
  description = "returns a number"
  value       = bigip_ltm_profile_client_ssl.this.generation
}

output "generic_alert" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.generic_alert
}

output "handshake_timeout" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.handshake_timeout
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.id
}

output "inherit_cert_keychain" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.inherit_cert_keychain
}

output "key" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.key
}

output "mod_ssl_methods" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.mod_ssl_methods
}

output "mode" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.mode
}

output "partition" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.partition
}

output "passphrase" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.passphrase
}

output "peer_cert_mode" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.peer_cert_mode
}

output "proxy_ca_cert" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.proxy_ca_cert
}

output "proxy_ca_key" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.proxy_ca_key
}

output "proxy_ca_passphrase" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.proxy_ca_passphrase
}

output "proxy_ssl" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.proxy_ssl
}

output "proxy_ssl_passthrough" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.proxy_ssl_passthrough
}

output "renegotiate_period" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.renegotiate_period
}

output "renegotiate_size" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.renegotiate_size
}

output "renegotiation" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.renegotiation
}

output "retain_certificate" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.retain_certificate
}

output "secure_renegotiation" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.secure_renegotiation
}

output "server_name" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.server_name
}

output "session_mirroring" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.session_mirroring
}

output "session_ticket" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.session_ticket
}

output "sni_default" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.sni_default
}

output "sni_require" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.sni_require
}

output "ssl_forward_proxy" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.ssl_forward_proxy
}

output "ssl_forward_proxy_bypass" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.ssl_forward_proxy_bypass
}

output "ssl_sign_hash" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.ssl_sign_hash
}

output "strict_resume" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.strict_resume
}

output "tm_options" {
  description = "returns a set of string"
  value       = bigip_ltm_profile_client_ssl.this.tm_options
}

output "unclean_shutdown" {
  description = "returns a string"
  value       = bigip_ltm_profile_client_ssl.this.unclean_shutdown
}

output "this" {
  value = bigip_ltm_profile_client_ssl.this
}
```

[top](#index)