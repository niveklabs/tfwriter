# fortios_vpnssl_settings

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
module "fortios_vpnssl_settings" {
  source = "./modules/fortios/r/fortios_vpnssl_settings"

  # algorithm - (optional) is a type of string
  algorithm = null
  # auth_session_check_source_ip - (optional) is a type of string
  auth_session_check_source_ip = null
  # auth_timeout - (optional) is a type of number
  auth_timeout = null
  # auto_tunnel_static_route - (optional) is a type of string
  auto_tunnel_static_route = null
  # banned_cipher - (optional) is a type of string
  banned_cipher = null
  # check_referer - (optional) is a type of string
  check_referer = null
  # default_portal - (optional) is a type of string
  default_portal = null
  # deflate_compression_level - (optional) is a type of number
  deflate_compression_level = null
  # deflate_min_data_size - (optional) is a type of number
  deflate_min_data_size = null
  # dns_server1 - (optional) is a type of string
  dns_server1 = null
  # dns_server2 - (optional) is a type of string
  dns_server2 = null
  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # dtls_hello_timeout - (optional) is a type of number
  dtls_hello_timeout = null
  # dtls_max_proto_ver - (optional) is a type of string
  dtls_max_proto_ver = null
  # dtls_min_proto_ver - (optional) is a type of string
  dtls_min_proto_ver = null
  # dtls_tunnel - (optional) is a type of string
  dtls_tunnel = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # encode_2f_sequence - (optional) is a type of string
  encode_2f_sequence = null
  # encrypt_and_store_password - (optional) is a type of string
  encrypt_and_store_password = null
  # force_two_factor_auth - (optional) is a type of string
  force_two_factor_auth = null
  # header_x_forwarded_for - (optional) is a type of string
  header_x_forwarded_for = null
  # hsts_include_subdomains - (optional) is a type of string
  hsts_include_subdomains = null
  # http_compression - (optional) is a type of string
  http_compression = null
  # http_only_cookie - (optional) is a type of string
  http_only_cookie = null
  # http_request_body_timeout - (optional) is a type of number
  http_request_body_timeout = null
  # http_request_header_timeout - (optional) is a type of number
  http_request_header_timeout = null
  # https_redirect - (optional) is a type of string
  https_redirect = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # ipv6_dns_server1 - (optional) is a type of string
  ipv6_dns_server1 = null
  # ipv6_dns_server2 - (optional) is a type of string
  ipv6_dns_server2 = null
  # ipv6_wins_server1 - (optional) is a type of string
  ipv6_wins_server1 = null
  # ipv6_wins_server2 - (optional) is a type of string
  ipv6_wins_server2 = null
  # login_attempt_limit - (optional) is a type of number
  login_attempt_limit = null
  # login_block_time - (optional) is a type of number
  login_block_time = null
  # login_timeout - (optional) is a type of number
  login_timeout = null
  # port - (optional) is a type of number
  port = null
  # port_precedence - (optional) is a type of string
  port_precedence = null
  # reqclientcert - (optional) is a type of string
  reqclientcert = null
  # route_source_interface - (optional) is a type of string
  route_source_interface = null
  # servercert - (optional) is a type of string
  servercert = null
  # source_address6_negate - (optional) is a type of string
  source_address6_negate = null
  # source_address_negate - (optional) is a type of string
  source_address_negate = null
  # ssl_client_renegotiation - (optional) is a type of string
  ssl_client_renegotiation = null
  # ssl_insert_empty_fragment - (optional) is a type of string
  ssl_insert_empty_fragment = null
  # ssl_max_proto_ver - (optional) is a type of string
  ssl_max_proto_ver = null
  # ssl_min_proto_ver - (optional) is a type of string
  ssl_min_proto_ver = null
  # tlsv1_0 - (optional) is a type of string
  tlsv1_0 = null
  # tlsv1_1 - (optional) is a type of string
  tlsv1_1 = null
  # tlsv1_2 - (optional) is a type of string
  tlsv1_2 = null
  # tlsv1_3 - (optional) is a type of string
  tlsv1_3 = null
  # transform_backward_slashes - (optional) is a type of string
  transform_backward_slashes = null
  # tunnel_connect_without_reauth - (optional) is a type of string
  tunnel_connect_without_reauth = null
  # tunnel_user_session_timeout - (optional) is a type of number
  tunnel_user_session_timeout = null
  # unsafe_legacy_renegotiation - (optional) is a type of string
  unsafe_legacy_renegotiation = null
  # url_obscuration - (optional) is a type of string
  url_obscuration = null
  # user_peer - (optional) is a type of string
  user_peer = null
  # wins_server1 - (optional) is a type of string
  wins_server1 = null
  # wins_server2 - (optional) is a type of string
  wins_server2 = null
  # x_content_type_options - (optional) is a type of string
  x_content_type_options = null

  authentication_rule = [{
    auth        = null
    cipher      = null
    client_cert = null
    groups = [{
      name = null
    }]
    id     = null
    portal = null
    realm  = null
    source_address = [{
      name = null
    }]
    source_address6 = [{
      name = null
    }]
    source_address6_negate = null
    source_address_negate  = null
    source_interface = [{
      name = null
    }]
    user_peer = null
    users = [{
      name = null
    }]
  }]

  source_address = [{
    name = null
  }]

  source_address6 = [{
    name = null
  }]

  source_interface = [{
    name = null
  }]

  tunnel_ip_pools = [{
    name = null
  }]

  tunnel_ipv6_pools = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_session_check_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_tunnel_static_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "banned_cipher" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_referer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_portal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deflate_compression_level" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "deflate_min_data_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_suffix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dtls_hello_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dtls_max_proto_ver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dtls_min_proto_ver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dtls_tunnel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encode_2f_sequence" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypt_and_store_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_two_factor_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_x_forwarded_for" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hsts_include_subdomains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_compression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_only_cookie" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_request_body_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_request_header_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "https_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_wins_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_wins_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_attempt_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "login_block_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "login_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_precedence" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reqclientcert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_source_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "servercert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_address6_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_address_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_client_renegotiation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_insert_empty_fragment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_max_proto_ver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_ver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tlsv1_0" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tlsv1_1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tlsv1_2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tlsv1_3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transform_backward_slashes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_connect_without_reauth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_user_session_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "unsafe_legacy_renegotiation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_obscuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_peer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wins_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wins_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "x_content_type_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authentication_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth        = string
      cipher      = string
      client_cert = string
      groups = list(object(
        {
          name = string
        }
      ))
      id     = number
      portal = string
      realm  = string
      source_address = list(object(
        {
          name = string
        }
      ))
      source_address6 = list(object(
        {
          name = string
        }
      ))
      source_address6_negate = string
      source_address_negate  = string
      source_interface = list(object(
        {
          name = string
        }
      ))
      user_peer = string
      users = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "source_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "source_address6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "source_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "tunnel_ip_pools" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "tunnel_ipv6_pools" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnssl_settings" "this" {
  algorithm                     = var.algorithm
  auth_session_check_source_ip  = var.auth_session_check_source_ip
  auth_timeout                  = var.auth_timeout
  auto_tunnel_static_route      = var.auto_tunnel_static_route
  banned_cipher                 = var.banned_cipher
  check_referer                 = var.check_referer
  default_portal                = var.default_portal
  deflate_compression_level     = var.deflate_compression_level
  deflate_min_data_size         = var.deflate_min_data_size
  dns_server1                   = var.dns_server1
  dns_server2                   = var.dns_server2
  dns_suffix                    = var.dns_suffix
  dtls_hello_timeout            = var.dtls_hello_timeout
  dtls_max_proto_ver            = var.dtls_max_proto_ver
  dtls_min_proto_ver            = var.dtls_min_proto_ver
  dtls_tunnel                   = var.dtls_tunnel
  dynamic_sort_subtable         = var.dynamic_sort_subtable
  encode_2f_sequence            = var.encode_2f_sequence
  encrypt_and_store_password    = var.encrypt_and_store_password
  force_two_factor_auth         = var.force_two_factor_auth
  header_x_forwarded_for        = var.header_x_forwarded_for
  hsts_include_subdomains       = var.hsts_include_subdomains
  http_compression              = var.http_compression
  http_only_cookie              = var.http_only_cookie
  http_request_body_timeout     = var.http_request_body_timeout
  http_request_header_timeout   = var.http_request_header_timeout
  https_redirect                = var.https_redirect
  idle_timeout                  = var.idle_timeout
  ipv6_dns_server1              = var.ipv6_dns_server1
  ipv6_dns_server2              = var.ipv6_dns_server2
  ipv6_wins_server1             = var.ipv6_wins_server1
  ipv6_wins_server2             = var.ipv6_wins_server2
  login_attempt_limit           = var.login_attempt_limit
  login_block_time              = var.login_block_time
  login_timeout                 = var.login_timeout
  port                          = var.port
  port_precedence               = var.port_precedence
  reqclientcert                 = var.reqclientcert
  route_source_interface        = var.route_source_interface
  servercert                    = var.servercert
  source_address6_negate        = var.source_address6_negate
  source_address_negate         = var.source_address_negate
  ssl_client_renegotiation      = var.ssl_client_renegotiation
  ssl_insert_empty_fragment     = var.ssl_insert_empty_fragment
  ssl_max_proto_ver             = var.ssl_max_proto_ver
  ssl_min_proto_ver             = var.ssl_min_proto_ver
  tlsv1_0                       = var.tlsv1_0
  tlsv1_1                       = var.tlsv1_1
  tlsv1_2                       = var.tlsv1_2
  tlsv1_3                       = var.tlsv1_3
  transform_backward_slashes    = var.transform_backward_slashes
  tunnel_connect_without_reauth = var.tunnel_connect_without_reauth
  tunnel_user_session_timeout   = var.tunnel_user_session_timeout
  unsafe_legacy_renegotiation   = var.unsafe_legacy_renegotiation
  url_obscuration               = var.url_obscuration
  user_peer                     = var.user_peer
  wins_server1                  = var.wins_server1
  wins_server2                  = var.wins_server2
  x_content_type_options        = var.x_content_type_options

  dynamic "authentication_rule" {
    for_each = var.authentication_rule
    content {
      auth                   = authentication_rule.value["auth"]
      cipher                 = authentication_rule.value["cipher"]
      client_cert            = authentication_rule.value["client_cert"]
      id                     = authentication_rule.value["id"]
      portal                 = authentication_rule.value["portal"]
      realm                  = authentication_rule.value["realm"]
      source_address6_negate = authentication_rule.value["source_address6_negate"]
      source_address_negate  = authentication_rule.value["source_address_negate"]
      user_peer              = authentication_rule.value["user_peer"]

      dynamic "groups" {
        for_each = authentication_rule.value.groups
        content {
          name = groups.value["name"]
        }
      }

      dynamic "source_address" {
        for_each = authentication_rule.value.source_address
        content {
          name = source_address.value["name"]
        }
      }

      dynamic "source_address6" {
        for_each = authentication_rule.value.source_address6
        content {
          name = source_address6.value["name"]
        }
      }

      dynamic "source_interface" {
        for_each = authentication_rule.value.source_interface
        content {
          name = source_interface.value["name"]
        }
      }

      dynamic "users" {
        for_each = authentication_rule.value.users
        content {
          name = users.value["name"]
        }
      }

    }
  }

  dynamic "source_address" {
    for_each = var.source_address
    content {
      name = source_address.value["name"]
    }
  }

  dynamic "source_address6" {
    for_each = var.source_address6
    content {
      name = source_address6.value["name"]
    }
  }

  dynamic "source_interface" {
    for_each = var.source_interface
    content {
      name = source_interface.value["name"]
    }
  }

  dynamic "tunnel_ip_pools" {
    for_each = var.tunnel_ip_pools
    content {
      name = tunnel_ip_pools.value["name"]
    }
  }

  dynamic "tunnel_ipv6_pools" {
    for_each = var.tunnel_ipv6_pools
    content {
      name = tunnel_ipv6_pools.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.algorithm
}

output "auth_session_check_source_ip" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.auth_session_check_source_ip
}

output "auth_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.auth_timeout
}

output "auto_tunnel_static_route" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.auto_tunnel_static_route
}

output "banned_cipher" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.banned_cipher
}

output "check_referer" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.check_referer
}

output "default_portal" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.default_portal
}

output "deflate_compression_level" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.deflate_compression_level
}

output "deflate_min_data_size" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.deflate_min_data_size
}

output "dns_server1" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.dns_server1
}

output "dns_server2" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.dns_server2
}

output "dtls_hello_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.dtls_hello_timeout
}

output "dtls_max_proto_ver" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.dtls_max_proto_ver
}

output "dtls_min_proto_ver" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.dtls_min_proto_ver
}

output "dtls_tunnel" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.dtls_tunnel
}

output "encode_2f_sequence" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.encode_2f_sequence
}

output "encrypt_and_store_password" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.encrypt_and_store_password
}

output "force_two_factor_auth" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.force_two_factor_auth
}

output "header_x_forwarded_for" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.header_x_forwarded_for
}

output "hsts_include_subdomains" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.hsts_include_subdomains
}

output "http_compression" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.http_compression
}

output "http_only_cookie" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.http_only_cookie
}

output "http_request_body_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.http_request_body_timeout
}

output "http_request_header_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.http_request_header_timeout
}

output "https_redirect" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.https_redirect
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.id
}

output "idle_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.idle_timeout
}

output "ipv6_dns_server1" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ipv6_dns_server1
}

output "ipv6_dns_server2" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ipv6_dns_server2
}

output "ipv6_wins_server1" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ipv6_wins_server1
}

output "ipv6_wins_server2" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ipv6_wins_server2
}

output "login_attempt_limit" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.login_attempt_limit
}

output "login_block_time" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.login_block_time
}

output "login_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.login_timeout
}

output "port" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.port
}

output "port_precedence" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.port_precedence
}

output "reqclientcert" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.reqclientcert
}

output "route_source_interface" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.route_source_interface
}

output "servercert" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.servercert
}

output "source_address6_negate" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.source_address6_negate
}

output "source_address_negate" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.source_address_negate
}

output "ssl_client_renegotiation" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ssl_client_renegotiation
}

output "ssl_insert_empty_fragment" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ssl_insert_empty_fragment
}

output "ssl_max_proto_ver" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ssl_max_proto_ver
}

output "ssl_min_proto_ver" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.ssl_min_proto_ver
}

output "tlsv1_0" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.tlsv1_0
}

output "tlsv1_1" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.tlsv1_1
}

output "tlsv1_2" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.tlsv1_2
}

output "tlsv1_3" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.tlsv1_3
}

output "transform_backward_slashes" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.transform_backward_slashes
}

output "tunnel_connect_without_reauth" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.tunnel_connect_without_reauth
}

output "tunnel_user_session_timeout" {
  description = "returns a number"
  value       = fortios_vpnssl_settings.this.tunnel_user_session_timeout
}

output "unsafe_legacy_renegotiation" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.unsafe_legacy_renegotiation
}

output "url_obscuration" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.url_obscuration
}

output "user_peer" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.user_peer
}

output "wins_server1" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.wins_server1
}

output "wins_server2" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.wins_server2
}

output "x_content_type_options" {
  description = "returns a string"
  value       = fortios_vpnssl_settings.this.x_content_type_options
}

output "this" {
  value = fortios_vpnssl_settings.this
}
```

[top](#index)