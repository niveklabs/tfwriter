# fortios_firewall_sslsshprofile

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
module "fortios_firewall_sslsshprofile" {
  source = "./modules/fortios/r/fortios_firewall_sslsshprofile"

  # allowlist - (optional) is a type of string
  allowlist = null
  # block_blacklisted_certificates - (optional) is a type of string
  block_blacklisted_certificates = null
  # block_blocklisted_certificates - (optional) is a type of string
  block_blocklisted_certificates = null
  # caname - (optional) is a type of string
  caname = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # mapi_over_https - (optional) is a type of string
  mapi_over_https = null
  # name - (required) is a type of string
  name = null
  # rpc_over_https - (optional) is a type of string
  rpc_over_https = null
  # server_cert - (optional) is a type of string
  server_cert = null
  # server_cert_mode - (optional) is a type of string
  server_cert_mode = null
  # ssl_anomalies_log - (optional) is a type of string
  ssl_anomalies_log = null
  # ssl_exemptions_log - (optional) is a type of string
  ssl_exemptions_log = null
  # ssl_negotiation_log - (optional) is a type of string
  ssl_negotiation_log = null
  # supported_alpn - (optional) is a type of string
  supported_alpn = null
  # untrusted_caname - (optional) is a type of string
  untrusted_caname = null
  # use_ssl_server - (optional) is a type of string
  use_ssl_server = null
  # whitelist - (optional) is a type of string
  whitelist = null

  ftps = [{
    cert_validation_failure     = null
    cert_validation_timeout     = null
    client_cert_request         = null
    client_certificate          = null
    expired_server_cert         = null
    invalid_server_cert         = null
    ports                       = null
    revoked_server_cert         = null
    sni_server_cert_check       = null
    status                      = null
    unsupported_ssl             = null
    unsupported_ssl_cipher      = null
    unsupported_ssl_negotiation = null
    untrusted_server_cert       = null
  }]

  https = [{
    cert_validation_failure     = null
    cert_validation_timeout     = null
    client_cert_request         = null
    client_certificate          = null
    expired_server_cert         = null
    invalid_server_cert         = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    revoked_server_cert         = null
    sni_server_cert_check       = null
    status                      = null
    unsupported_ssl             = null
    unsupported_ssl_cipher      = null
    unsupported_ssl_negotiation = null
    untrusted_server_cert       = null
  }]

  imaps = [{
    cert_validation_failure     = null
    cert_validation_timeout     = null
    client_cert_request         = null
    client_certificate          = null
    expired_server_cert         = null
    invalid_server_cert         = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    revoked_server_cert         = null
    sni_server_cert_check       = null
    status                      = null
    unsupported_ssl             = null
    unsupported_ssl_cipher      = null
    unsupported_ssl_negotiation = null
    untrusted_server_cert       = null
  }]

  pop3s = [{
    cert_validation_failure     = null
    cert_validation_timeout     = null
    client_cert_request         = null
    client_certificate          = null
    expired_server_cert         = null
    invalid_server_cert         = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    revoked_server_cert         = null
    sni_server_cert_check       = null
    status                      = null
    unsupported_ssl             = null
    unsupported_ssl_cipher      = null
    unsupported_ssl_negotiation = null
    untrusted_server_cert       = null
  }]

  smtps = [{
    cert_validation_failure     = null
    cert_validation_timeout     = null
    client_cert_request         = null
    client_certificate          = null
    expired_server_cert         = null
    invalid_server_cert         = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    revoked_server_cert         = null
    sni_server_cert_check       = null
    status                      = null
    unsupported_ssl             = null
    unsupported_ssl_cipher      = null
    unsupported_ssl_negotiation = null
    untrusted_server_cert       = null
  }]

  ssh = [{
    inspect_all               = null
    ports                     = null
    proxy_after_tcp_handshake = null
    ssh_algorithm             = null
    ssh_policy_check          = null
    ssh_tun_policy_check      = null
    status                    = null
    unsupported_version       = null
  }]

  ssl = [{
    cert_validation_failure     = null
    cert_validation_timeout     = null
    client_cert_request         = null
    client_certificate          = null
    expired_server_cert         = null
    inspect_all                 = null
    invalid_server_cert         = null
    revoked_server_cert         = null
    sni_server_cert_check       = null
    unsupported_ssl             = null
    unsupported_ssl_cipher      = null
    unsupported_ssl_negotiation = null
    untrusted_server_cert       = null
  }]

  ssl_exempt = [{
    address             = null
    address6            = null
    fortiguard_category = null
    id                  = null
    regex               = null
    type                = null
    wildcard_fqdn       = null
  }]

  ssl_server = [{
    ftps_client_cert_request      = null
    ftps_client_certificate       = null
    https_client_cert_request     = null
    https_client_certificate      = null
    id                            = null
    imaps_client_cert_request     = null
    imaps_client_certificate      = null
    ip                            = null
    pop3s_client_cert_request     = null
    pop3s_client_certificate      = null
    smtps_client_cert_request     = null
    smtps_client_certificate      = null
    ssl_other_client_cert_request = null
    ssl_other_client_certificate  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowlist" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_blacklisted_certificates" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_blocklisted_certificates" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "caname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mapi_over_https" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rpc_over_https" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_cert_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_anomalies_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_exemptions_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_negotiation_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "supported_alpn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "untrusted_caname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_ssl_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "whitelist" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftps" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_validation_failure     = string
      cert_validation_timeout     = string
      client_cert_request         = string
      client_certificate          = string
      expired_server_cert         = string
      invalid_server_cert         = string
      ports                       = string
      revoked_server_cert         = string
      sni_server_cert_check       = string
      status                      = string
      unsupported_ssl             = string
      unsupported_ssl_cipher      = string
      unsupported_ssl_negotiation = string
      untrusted_server_cert       = string
    }
  ))
  default = []
}

variable "https" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_validation_failure     = string
      cert_validation_timeout     = string
      client_cert_request         = string
      client_certificate          = string
      expired_server_cert         = string
      invalid_server_cert         = string
      ports                       = string
      proxy_after_tcp_handshake   = string
      revoked_server_cert         = string
      sni_server_cert_check       = string
      status                      = string
      unsupported_ssl             = string
      unsupported_ssl_cipher      = string
      unsupported_ssl_negotiation = string
      untrusted_server_cert       = string
    }
  ))
  default = []
}

variable "imaps" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_validation_failure     = string
      cert_validation_timeout     = string
      client_cert_request         = string
      client_certificate          = string
      expired_server_cert         = string
      invalid_server_cert         = string
      ports                       = string
      proxy_after_tcp_handshake   = string
      revoked_server_cert         = string
      sni_server_cert_check       = string
      status                      = string
      unsupported_ssl             = string
      unsupported_ssl_cipher      = string
      unsupported_ssl_negotiation = string
      untrusted_server_cert       = string
    }
  ))
  default = []
}

variable "pop3s" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_validation_failure     = string
      cert_validation_timeout     = string
      client_cert_request         = string
      client_certificate          = string
      expired_server_cert         = string
      invalid_server_cert         = string
      ports                       = string
      proxy_after_tcp_handshake   = string
      revoked_server_cert         = string
      sni_server_cert_check       = string
      status                      = string
      unsupported_ssl             = string
      unsupported_ssl_cipher      = string
      unsupported_ssl_negotiation = string
      untrusted_server_cert       = string
    }
  ))
  default = []
}

variable "smtps" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_validation_failure     = string
      cert_validation_timeout     = string
      client_cert_request         = string
      client_certificate          = string
      expired_server_cert         = string
      invalid_server_cert         = string
      ports                       = string
      proxy_after_tcp_handshake   = string
      revoked_server_cert         = string
      sni_server_cert_check       = string
      status                      = string
      unsupported_ssl             = string
      unsupported_ssl_cipher      = string
      unsupported_ssl_negotiation = string
      untrusted_server_cert       = string
    }
  ))
  default = []
}

variable "ssh" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inspect_all               = string
      ports                     = string
      proxy_after_tcp_handshake = string
      ssh_algorithm             = string
      ssh_policy_check          = string
      ssh_tun_policy_check      = string
      status                    = string
      unsupported_version       = string
    }
  ))
  default = []
}

variable "ssl" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_validation_failure     = string
      cert_validation_timeout     = string
      client_cert_request         = string
      client_certificate          = string
      expired_server_cert         = string
      inspect_all                 = string
      invalid_server_cert         = string
      revoked_server_cert         = string
      sni_server_cert_check       = string
      unsupported_ssl             = string
      unsupported_ssl_cipher      = string
      unsupported_ssl_negotiation = string
      untrusted_server_cert       = string
    }
  ))
  default = []
}

variable "ssl_exempt" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      address             = string
      address6            = string
      fortiguard_category = number
      id                  = number
      regex               = string
      type                = string
      wildcard_fqdn       = string
    }
  ))
  default = []
}

variable "ssl_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ftps_client_cert_request      = string
      ftps_client_certificate       = string
      https_client_cert_request     = string
      https_client_certificate      = string
      id                            = number
      imaps_client_cert_request     = string
      imaps_client_certificate      = string
      ip                            = string
      pop3s_client_cert_request     = string
      pop3s_client_certificate      = string
      smtps_client_cert_request     = string
      smtps_client_certificate      = string
      ssl_other_client_cert_request = string
      ssl_other_client_certificate  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_sslsshprofile" "this" {
  allowlist                      = var.allowlist
  block_blacklisted_certificates = var.block_blacklisted_certificates
  block_blocklisted_certificates = var.block_blocklisted_certificates
  caname                         = var.caname
  comment                        = var.comment
  dynamic_sort_subtable          = var.dynamic_sort_subtable
  mapi_over_https                = var.mapi_over_https
  name                           = var.name
  rpc_over_https                 = var.rpc_over_https
  server_cert                    = var.server_cert
  server_cert_mode               = var.server_cert_mode
  ssl_anomalies_log              = var.ssl_anomalies_log
  ssl_exemptions_log             = var.ssl_exemptions_log
  ssl_negotiation_log            = var.ssl_negotiation_log
  supported_alpn                 = var.supported_alpn
  untrusted_caname               = var.untrusted_caname
  use_ssl_server                 = var.use_ssl_server
  whitelist                      = var.whitelist

  dynamic "ftps" {
    for_each = var.ftps
    content {
      cert_validation_failure     = ftps.value["cert_validation_failure"]
      cert_validation_timeout     = ftps.value["cert_validation_timeout"]
      client_cert_request         = ftps.value["client_cert_request"]
      client_certificate          = ftps.value["client_certificate"]
      expired_server_cert         = ftps.value["expired_server_cert"]
      invalid_server_cert         = ftps.value["invalid_server_cert"]
      ports                       = ftps.value["ports"]
      revoked_server_cert         = ftps.value["revoked_server_cert"]
      sni_server_cert_check       = ftps.value["sni_server_cert_check"]
      status                      = ftps.value["status"]
      unsupported_ssl             = ftps.value["unsupported_ssl"]
      unsupported_ssl_cipher      = ftps.value["unsupported_ssl_cipher"]
      unsupported_ssl_negotiation = ftps.value["unsupported_ssl_negotiation"]
      untrusted_server_cert       = ftps.value["untrusted_server_cert"]
    }
  }

  dynamic "https" {
    for_each = var.https
    content {
      cert_validation_failure     = https.value["cert_validation_failure"]
      cert_validation_timeout     = https.value["cert_validation_timeout"]
      client_cert_request         = https.value["client_cert_request"]
      client_certificate          = https.value["client_certificate"]
      expired_server_cert         = https.value["expired_server_cert"]
      invalid_server_cert         = https.value["invalid_server_cert"]
      ports                       = https.value["ports"]
      proxy_after_tcp_handshake   = https.value["proxy_after_tcp_handshake"]
      revoked_server_cert         = https.value["revoked_server_cert"]
      sni_server_cert_check       = https.value["sni_server_cert_check"]
      status                      = https.value["status"]
      unsupported_ssl             = https.value["unsupported_ssl"]
      unsupported_ssl_cipher      = https.value["unsupported_ssl_cipher"]
      unsupported_ssl_negotiation = https.value["unsupported_ssl_negotiation"]
      untrusted_server_cert       = https.value["untrusted_server_cert"]
    }
  }

  dynamic "imaps" {
    for_each = var.imaps
    content {
      cert_validation_failure     = imaps.value["cert_validation_failure"]
      cert_validation_timeout     = imaps.value["cert_validation_timeout"]
      client_cert_request         = imaps.value["client_cert_request"]
      client_certificate          = imaps.value["client_certificate"]
      expired_server_cert         = imaps.value["expired_server_cert"]
      invalid_server_cert         = imaps.value["invalid_server_cert"]
      ports                       = imaps.value["ports"]
      proxy_after_tcp_handshake   = imaps.value["proxy_after_tcp_handshake"]
      revoked_server_cert         = imaps.value["revoked_server_cert"]
      sni_server_cert_check       = imaps.value["sni_server_cert_check"]
      status                      = imaps.value["status"]
      unsupported_ssl             = imaps.value["unsupported_ssl"]
      unsupported_ssl_cipher      = imaps.value["unsupported_ssl_cipher"]
      unsupported_ssl_negotiation = imaps.value["unsupported_ssl_negotiation"]
      untrusted_server_cert       = imaps.value["untrusted_server_cert"]
    }
  }

  dynamic "pop3s" {
    for_each = var.pop3s
    content {
      cert_validation_failure     = pop3s.value["cert_validation_failure"]
      cert_validation_timeout     = pop3s.value["cert_validation_timeout"]
      client_cert_request         = pop3s.value["client_cert_request"]
      client_certificate          = pop3s.value["client_certificate"]
      expired_server_cert         = pop3s.value["expired_server_cert"]
      invalid_server_cert         = pop3s.value["invalid_server_cert"]
      ports                       = pop3s.value["ports"]
      proxy_after_tcp_handshake   = pop3s.value["proxy_after_tcp_handshake"]
      revoked_server_cert         = pop3s.value["revoked_server_cert"]
      sni_server_cert_check       = pop3s.value["sni_server_cert_check"]
      status                      = pop3s.value["status"]
      unsupported_ssl             = pop3s.value["unsupported_ssl"]
      unsupported_ssl_cipher      = pop3s.value["unsupported_ssl_cipher"]
      unsupported_ssl_negotiation = pop3s.value["unsupported_ssl_negotiation"]
      untrusted_server_cert       = pop3s.value["untrusted_server_cert"]
    }
  }

  dynamic "smtps" {
    for_each = var.smtps
    content {
      cert_validation_failure     = smtps.value["cert_validation_failure"]
      cert_validation_timeout     = smtps.value["cert_validation_timeout"]
      client_cert_request         = smtps.value["client_cert_request"]
      client_certificate          = smtps.value["client_certificate"]
      expired_server_cert         = smtps.value["expired_server_cert"]
      invalid_server_cert         = smtps.value["invalid_server_cert"]
      ports                       = smtps.value["ports"]
      proxy_after_tcp_handshake   = smtps.value["proxy_after_tcp_handshake"]
      revoked_server_cert         = smtps.value["revoked_server_cert"]
      sni_server_cert_check       = smtps.value["sni_server_cert_check"]
      status                      = smtps.value["status"]
      unsupported_ssl             = smtps.value["unsupported_ssl"]
      unsupported_ssl_cipher      = smtps.value["unsupported_ssl_cipher"]
      unsupported_ssl_negotiation = smtps.value["unsupported_ssl_negotiation"]
      untrusted_server_cert       = smtps.value["untrusted_server_cert"]
    }
  }

  dynamic "ssh" {
    for_each = var.ssh
    content {
      inspect_all               = ssh.value["inspect_all"]
      ports                     = ssh.value["ports"]
      proxy_after_tcp_handshake = ssh.value["proxy_after_tcp_handshake"]
      ssh_algorithm             = ssh.value["ssh_algorithm"]
      ssh_policy_check          = ssh.value["ssh_policy_check"]
      ssh_tun_policy_check      = ssh.value["ssh_tun_policy_check"]
      status                    = ssh.value["status"]
      unsupported_version       = ssh.value["unsupported_version"]
    }
  }

  dynamic "ssl" {
    for_each = var.ssl
    content {
      cert_validation_failure     = ssl.value["cert_validation_failure"]
      cert_validation_timeout     = ssl.value["cert_validation_timeout"]
      client_cert_request         = ssl.value["client_cert_request"]
      client_certificate          = ssl.value["client_certificate"]
      expired_server_cert         = ssl.value["expired_server_cert"]
      inspect_all                 = ssl.value["inspect_all"]
      invalid_server_cert         = ssl.value["invalid_server_cert"]
      revoked_server_cert         = ssl.value["revoked_server_cert"]
      sni_server_cert_check       = ssl.value["sni_server_cert_check"]
      unsupported_ssl             = ssl.value["unsupported_ssl"]
      unsupported_ssl_cipher      = ssl.value["unsupported_ssl_cipher"]
      unsupported_ssl_negotiation = ssl.value["unsupported_ssl_negotiation"]
      untrusted_server_cert       = ssl.value["untrusted_server_cert"]
    }
  }

  dynamic "ssl_exempt" {
    for_each = var.ssl_exempt
    content {
      address             = ssl_exempt.value["address"]
      address6            = ssl_exempt.value["address6"]
      fortiguard_category = ssl_exempt.value["fortiguard_category"]
      id                  = ssl_exempt.value["id"]
      regex               = ssl_exempt.value["regex"]
      type                = ssl_exempt.value["type"]
      wildcard_fqdn       = ssl_exempt.value["wildcard_fqdn"]
    }
  }

  dynamic "ssl_server" {
    for_each = var.ssl_server
    content {
      ftps_client_cert_request      = ssl_server.value["ftps_client_cert_request"]
      ftps_client_certificate       = ssl_server.value["ftps_client_certificate"]
      https_client_cert_request     = ssl_server.value["https_client_cert_request"]
      https_client_certificate      = ssl_server.value["https_client_certificate"]
      id                            = ssl_server.value["id"]
      imaps_client_cert_request     = ssl_server.value["imaps_client_cert_request"]
      imaps_client_certificate      = ssl_server.value["imaps_client_certificate"]
      ip                            = ssl_server.value["ip"]
      pop3s_client_cert_request     = ssl_server.value["pop3s_client_cert_request"]
      pop3s_client_certificate      = ssl_server.value["pop3s_client_certificate"]
      smtps_client_cert_request     = ssl_server.value["smtps_client_cert_request"]
      smtps_client_certificate      = ssl_server.value["smtps_client_certificate"]
      ssl_other_client_cert_request = ssl_server.value["ssl_other_client_cert_request"]
      ssl_other_client_certificate  = ssl_server.value["ssl_other_client_certificate"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allowlist" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.allowlist
}

output "block_blacklisted_certificates" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.block_blacklisted_certificates
}

output "block_blocklisted_certificates" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.block_blocklisted_certificates
}

output "caname" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.caname
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.id
}

output "mapi_over_https" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.mapi_over_https
}

output "rpc_over_https" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.rpc_over_https
}

output "server_cert" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.server_cert
}

output "server_cert_mode" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.server_cert_mode
}

output "ssl_anomalies_log" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.ssl_anomalies_log
}

output "ssl_exemptions_log" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.ssl_exemptions_log
}

output "ssl_negotiation_log" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.ssl_negotiation_log
}

output "supported_alpn" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.supported_alpn
}

output "untrusted_caname" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.untrusted_caname
}

output "use_ssl_server" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.use_ssl_server
}

output "whitelist" {
  description = "returns a string"
  value       = fortios_firewall_sslsshprofile.this.whitelist
}

output "this" {
  value = fortios_firewall_sslsshprofile.this
}
```

[top](#index)