# fortios_firewall_vip6

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_vip6" {
  source = "./modules/fortios/r/fortios_firewall_vip6"

  # arp_reply - (optional) is a type of string
  arp_reply = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # extip - (required) is a type of string
  extip = null
  # extport - (optional) is a type of string
  extport = null
  # fosid - (optional) is a type of number
  fosid = null
  # http_cookie_age - (optional) is a type of number
  http_cookie_age = null
  # http_cookie_domain - (optional) is a type of string
  http_cookie_domain = null
  # http_cookie_domain_from_host - (optional) is a type of string
  http_cookie_domain_from_host = null
  # http_cookie_generation - (optional) is a type of number
  http_cookie_generation = null
  # http_cookie_path - (optional) is a type of string
  http_cookie_path = null
  # http_cookie_share - (optional) is a type of string
  http_cookie_share = null
  # http_ip_header - (optional) is a type of string
  http_ip_header = null
  # http_ip_header_name - (optional) is a type of string
  http_ip_header_name = null
  # http_multiplex - (optional) is a type of string
  http_multiplex = null
  # https_cookie_secure - (optional) is a type of string
  https_cookie_secure = null
  # ldb_method - (optional) is a type of string
  ldb_method = null
  # mappedip - (required) is a type of string
  mappedip = null
  # mappedport - (optional) is a type of string
  mappedport = null
  # max_embryonic_connections - (optional) is a type of number
  max_embryonic_connections = null
  # name - (optional) is a type of string
  name = null
  # outlook_web_access - (optional) is a type of string
  outlook_web_access = null
  # persistence - (optional) is a type of string
  persistence = null
  # portforward - (optional) is a type of string
  portforward = null
  # protocol - (optional) is a type of string
  protocol = null
  # server_type - (optional) is a type of string
  server_type = null
  # ssl_algorithm - (optional) is a type of string
  ssl_algorithm = null
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = null
  # ssl_client_fallback - (optional) is a type of string
  ssl_client_fallback = null
  # ssl_client_renegotiation - (optional) is a type of string
  ssl_client_renegotiation = null
  # ssl_client_session_state_max - (optional) is a type of number
  ssl_client_session_state_max = null
  # ssl_client_session_state_timeout - (optional) is a type of number
  ssl_client_session_state_timeout = null
  # ssl_client_session_state_type - (optional) is a type of string
  ssl_client_session_state_type = null
  # ssl_dh_bits - (optional) is a type of string
  ssl_dh_bits = null
  # ssl_hpkp - (optional) is a type of string
  ssl_hpkp = null
  # ssl_hpkp_age - (optional) is a type of number
  ssl_hpkp_age = null
  # ssl_hpkp_backup - (optional) is a type of string
  ssl_hpkp_backup = null
  # ssl_hpkp_include_subdomains - (optional) is a type of string
  ssl_hpkp_include_subdomains = null
  # ssl_hpkp_primary - (optional) is a type of string
  ssl_hpkp_primary = null
  # ssl_hpkp_report_uri - (optional) is a type of string
  ssl_hpkp_report_uri = null
  # ssl_hsts - (optional) is a type of string
  ssl_hsts = null
  # ssl_hsts_age - (optional) is a type of number
  ssl_hsts_age = null
  # ssl_hsts_include_subdomains - (optional) is a type of string
  ssl_hsts_include_subdomains = null
  # ssl_http_location_conversion - (optional) is a type of string
  ssl_http_location_conversion = null
  # ssl_http_match_host - (optional) is a type of string
  ssl_http_match_host = null
  # ssl_max_version - (optional) is a type of string
  ssl_max_version = null
  # ssl_min_version - (optional) is a type of string
  ssl_min_version = null
  # ssl_mode - (optional) is a type of string
  ssl_mode = null
  # ssl_pfs - (optional) is a type of string
  ssl_pfs = null
  # ssl_send_empty_frags - (optional) is a type of string
  ssl_send_empty_frags = null
  # ssl_server_algorithm - (optional) is a type of string
  ssl_server_algorithm = null
  # ssl_server_max_version - (optional) is a type of string
  ssl_server_max_version = null
  # ssl_server_min_version - (optional) is a type of string
  ssl_server_min_version = null
  # ssl_server_session_state_max - (optional) is a type of number
  ssl_server_session_state_max = null
  # ssl_server_session_state_timeout - (optional) is a type of number
  ssl_server_session_state_timeout = null
  # ssl_server_session_state_type - (optional) is a type of string
  ssl_server_session_state_type = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null
  # weblogic_server - (optional) is a type of string
  weblogic_server = null
  # websphere_server - (optional) is a type of string
  websphere_server = null

  monitor = [{
    name = null
  }]

  realservers = [{
    client_ip         = null
    healthcheck       = null
    holddown_interval = null
    http_host         = null
    id                = null
    ip                = null
    max_connections   = null
    monitor           = null
    port              = null
    status            = null
    weight            = null
  }]

  src_filter = [{
    range = null
  }]

  ssl_cipher_suites = [{
    cipher   = null
    priority = null
    versions = null
  }]

  ssl_server_cipher_suites = [{
    cipher   = null
    priority = null
    versions = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "arp_reply" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extip" {
  description = "(required)"
  type        = string
}

variable "extport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_cookie_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_cookie_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_cookie_domain_from_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_cookie_generation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_cookie_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_cookie_share" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_ip_header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_ip_header_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_multiplex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_cookie_secure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldb_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mappedip" {
  description = "(required)"
  type        = string
}

variable "mappedport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_embryonic_connections" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outlook_web_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "persistence" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "portforward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_client_fallback" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_client_renegotiation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_client_session_state_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_client_session_state_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_client_session_state_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_dh_bits" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hpkp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hpkp_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_hpkp_backup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hpkp_include_subdomains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hpkp_primary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hpkp_report_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hsts" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_hsts_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_hsts_include_subdomains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_http_location_conversion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_http_match_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_max_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_pfs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_send_empty_frags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_server_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_server_max_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_server_min_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_server_session_state_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_server_session_state_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_server_session_state_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weblogic_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "websphere_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "realservers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_ip         = string
      healthcheck       = string
      holddown_interval = number
      http_host         = string
      id                = number
      ip                = string
      max_connections   = number
      monitor           = string
      port              = number
      status            = string
      weight            = number
    }
  ))
  default = []
}

variable "src_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      range = string
    }
  ))
  default = []
}

variable "ssl_cipher_suites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cipher   = string
      priority = number
      versions = string
    }
  ))
  default = []
}

variable "ssl_server_cipher_suites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cipher   = string
      priority = number
      versions = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_vip6" "this" {
  arp_reply                        = var.arp_reply
  color                            = var.color
  comment                          = var.comment
  extip                            = var.extip
  extport                          = var.extport
  fosid                            = var.fosid
  http_cookie_age                  = var.http_cookie_age
  http_cookie_domain               = var.http_cookie_domain
  http_cookie_domain_from_host     = var.http_cookie_domain_from_host
  http_cookie_generation           = var.http_cookie_generation
  http_cookie_path                 = var.http_cookie_path
  http_cookie_share                = var.http_cookie_share
  http_ip_header                   = var.http_ip_header
  http_ip_header_name              = var.http_ip_header_name
  http_multiplex                   = var.http_multiplex
  https_cookie_secure              = var.https_cookie_secure
  ldb_method                       = var.ldb_method
  mappedip                         = var.mappedip
  mappedport                       = var.mappedport
  max_embryonic_connections        = var.max_embryonic_connections
  name                             = var.name
  outlook_web_access               = var.outlook_web_access
  persistence                      = var.persistence
  portforward                      = var.portforward
  protocol                         = var.protocol
  server_type                      = var.server_type
  ssl_algorithm                    = var.ssl_algorithm
  ssl_certificate                  = var.ssl_certificate
  ssl_client_fallback              = var.ssl_client_fallback
  ssl_client_renegotiation         = var.ssl_client_renegotiation
  ssl_client_session_state_max     = var.ssl_client_session_state_max
  ssl_client_session_state_timeout = var.ssl_client_session_state_timeout
  ssl_client_session_state_type    = var.ssl_client_session_state_type
  ssl_dh_bits                      = var.ssl_dh_bits
  ssl_hpkp                         = var.ssl_hpkp
  ssl_hpkp_age                     = var.ssl_hpkp_age
  ssl_hpkp_backup                  = var.ssl_hpkp_backup
  ssl_hpkp_include_subdomains      = var.ssl_hpkp_include_subdomains
  ssl_hpkp_primary                 = var.ssl_hpkp_primary
  ssl_hpkp_report_uri              = var.ssl_hpkp_report_uri
  ssl_hsts                         = var.ssl_hsts
  ssl_hsts_age                     = var.ssl_hsts_age
  ssl_hsts_include_subdomains      = var.ssl_hsts_include_subdomains
  ssl_http_location_conversion     = var.ssl_http_location_conversion
  ssl_http_match_host              = var.ssl_http_match_host
  ssl_max_version                  = var.ssl_max_version
  ssl_min_version                  = var.ssl_min_version
  ssl_mode                         = var.ssl_mode
  ssl_pfs                          = var.ssl_pfs
  ssl_send_empty_frags             = var.ssl_send_empty_frags
  ssl_server_algorithm             = var.ssl_server_algorithm
  ssl_server_max_version           = var.ssl_server_max_version
  ssl_server_min_version           = var.ssl_server_min_version
  ssl_server_session_state_max     = var.ssl_server_session_state_max
  ssl_server_session_state_timeout = var.ssl_server_session_state_timeout
  ssl_server_session_state_type    = var.ssl_server_session_state_type
  type                             = var.type
  uuid                             = var.uuid
  weblogic_server                  = var.weblogic_server
  websphere_server                 = var.websphere_server

  dynamic "monitor" {
    for_each = var.monitor
    content {
      name = monitor.value["name"]
    }
  }

  dynamic "realservers" {
    for_each = var.realservers
    content {
      client_ip         = realservers.value["client_ip"]
      healthcheck       = realservers.value["healthcheck"]
      holddown_interval = realservers.value["holddown_interval"]
      http_host         = realservers.value["http_host"]
      id                = realservers.value["id"]
      ip                = realservers.value["ip"]
      max_connections   = realservers.value["max_connections"]
      monitor           = realservers.value["monitor"]
      port              = realservers.value["port"]
      status            = realservers.value["status"]
      weight            = realservers.value["weight"]
    }
  }

  dynamic "src_filter" {
    for_each = var.src_filter
    content {
      range = src_filter.value["range"]
    }
  }

  dynamic "ssl_cipher_suites" {
    for_each = var.ssl_cipher_suites
    content {
      cipher   = ssl_cipher_suites.value["cipher"]
      priority = ssl_cipher_suites.value["priority"]
      versions = ssl_cipher_suites.value["versions"]
    }
  }

  dynamic "ssl_server_cipher_suites" {
    for_each = var.ssl_server_cipher_suites
    content {
      cipher   = ssl_server_cipher_suites.value["cipher"]
      priority = ssl_server_cipher_suites.value["priority"]
      versions = ssl_server_cipher_suites.value["versions"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arp_reply" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.arp_reply
}

output "color" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.color
}

output "extport" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.extport
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.fosid
}

output "http_cookie_age" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.http_cookie_age
}

output "http_cookie_domain" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_cookie_domain
}

output "http_cookie_domain_from_host" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_cookie_domain_from_host
}

output "http_cookie_generation" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.http_cookie_generation
}

output "http_cookie_path" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_cookie_path
}

output "http_cookie_share" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_cookie_share
}

output "http_ip_header" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_ip_header
}

output "http_ip_header_name" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_ip_header_name
}

output "http_multiplex" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.http_multiplex
}

output "https_cookie_secure" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.https_cookie_secure
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.id
}

output "ldb_method" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ldb_method
}

output "mappedport" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.mappedport
}

output "max_embryonic_connections" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.max_embryonic_connections
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.name
}

output "outlook_web_access" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.outlook_web_access
}

output "persistence" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.persistence
}

output "portforward" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.portforward
}

output "protocol" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.protocol
}

output "server_type" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.server_type
}

output "ssl_algorithm" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_algorithm
}

output "ssl_certificate" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_certificate
}

output "ssl_client_fallback" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_client_fallback
}

output "ssl_client_renegotiation" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_client_renegotiation
}

output "ssl_client_session_state_max" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.ssl_client_session_state_max
}

output "ssl_client_session_state_timeout" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.ssl_client_session_state_timeout
}

output "ssl_client_session_state_type" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_client_session_state_type
}

output "ssl_dh_bits" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_dh_bits
}

output "ssl_hpkp" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_hpkp
}

output "ssl_hpkp_age" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.ssl_hpkp_age
}

output "ssl_hpkp_backup" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_hpkp_backup
}

output "ssl_hpkp_include_subdomains" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_hpkp_include_subdomains
}

output "ssl_hpkp_primary" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_hpkp_primary
}

output "ssl_hsts" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_hsts
}

output "ssl_hsts_age" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.ssl_hsts_age
}

output "ssl_hsts_include_subdomains" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_hsts_include_subdomains
}

output "ssl_http_location_conversion" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_http_location_conversion
}

output "ssl_http_match_host" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_http_match_host
}

output "ssl_max_version" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_max_version
}

output "ssl_min_version" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_min_version
}

output "ssl_mode" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_mode
}

output "ssl_pfs" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_pfs
}

output "ssl_send_empty_frags" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_send_empty_frags
}

output "ssl_server_algorithm" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_server_algorithm
}

output "ssl_server_max_version" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_server_max_version
}

output "ssl_server_min_version" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_server_min_version
}

output "ssl_server_session_state_max" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.ssl_server_session_state_max
}

output "ssl_server_session_state_timeout" {
  description = "returns a number"
  value       = fortios_firewall_vip6.this.ssl_server_session_state_timeout
}

output "ssl_server_session_state_type" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.ssl_server_session_state_type
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.type
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.uuid
}

output "weblogic_server" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.weblogic_server
}

output "websphere_server" {
  description = "returns a string"
  value       = fortios_firewall_vip6.this.websphere_server
}

output "this" {
  value = fortios_firewall_vip6.this
}
```

[top](#index)