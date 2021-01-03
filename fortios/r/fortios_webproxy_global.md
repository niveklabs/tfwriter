# fortios_webproxy_global

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
module "fortios_webproxy_global" {
  source = "./modules/fortios/r/fortios_webproxy_global"

  # fast_policy_match - (optional) is a type of string
  fast_policy_match = null
  # forward_proxy_auth - (optional) is a type of string
  forward_proxy_auth = null
  # forward_server_affinity_timeout - (optional) is a type of number
  forward_server_affinity_timeout = null
  # learn_client_ip - (optional) is a type of string
  learn_client_ip = null
  # learn_client_ip_from_header - (optional) is a type of string
  learn_client_ip_from_header = null
  # max_message_length - (optional) is a type of number
  max_message_length = null
  # max_request_length - (optional) is a type of number
  max_request_length = null
  # max_waf_body_cache_length - (optional) is a type of number
  max_waf_body_cache_length = null
  # proxy_fqdn - (required) is a type of string
  proxy_fqdn = null
  # ssl_ca_cert - (optional) is a type of string
  ssl_ca_cert = null
  # ssl_cert - (optional) is a type of string
  ssl_cert = null
  # strict_web_check - (optional) is a type of string
  strict_web_check = null
  # tunnel_non_http - (optional) is a type of string
  tunnel_non_http = null
  # unknown_http_version - (optional) is a type of string
  unknown_http_version = null
  # webproxy_profile - (optional) is a type of string
  webproxy_profile = null

  learn_client_ip_srcaddr = [{
    name = null
  }]

  learn_client_ip_srcaddr6 = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "fast_policy_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_server_affinity_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "learn_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "learn_client_ip_from_header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_message_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_request_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_waf_body_cache_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy_fqdn" {
  description = "(required)"
  type        = string
}

variable "ssl_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_web_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_non_http" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unknown_http_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webproxy_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "learn_client_ip_srcaddr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "learn_client_ip_srcaddr6" {
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
resource "fortios_webproxy_global" "this" {
  fast_policy_match               = var.fast_policy_match
  forward_proxy_auth              = var.forward_proxy_auth
  forward_server_affinity_timeout = var.forward_server_affinity_timeout
  learn_client_ip                 = var.learn_client_ip
  learn_client_ip_from_header     = var.learn_client_ip_from_header
  max_message_length              = var.max_message_length
  max_request_length              = var.max_request_length
  max_waf_body_cache_length       = var.max_waf_body_cache_length
  proxy_fqdn                      = var.proxy_fqdn
  ssl_ca_cert                     = var.ssl_ca_cert
  ssl_cert                        = var.ssl_cert
  strict_web_check                = var.strict_web_check
  tunnel_non_http                 = var.tunnel_non_http
  unknown_http_version            = var.unknown_http_version
  webproxy_profile                = var.webproxy_profile

  dynamic "learn_client_ip_srcaddr" {
    for_each = var.learn_client_ip_srcaddr
    content {
      name = learn_client_ip_srcaddr.value["name"]
    }
  }

  dynamic "learn_client_ip_srcaddr6" {
    for_each = var.learn_client_ip_srcaddr6
    content {
      name = learn_client_ip_srcaddr6.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fast_policy_match" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.fast_policy_match
}

output "forward_proxy_auth" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.forward_proxy_auth
}

output "forward_server_affinity_timeout" {
  description = "returns a number"
  value       = fortios_webproxy_global.this.forward_server_affinity_timeout
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.id
}

output "learn_client_ip" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.learn_client_ip
}

output "learn_client_ip_from_header" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.learn_client_ip_from_header
}

output "max_message_length" {
  description = "returns a number"
  value       = fortios_webproxy_global.this.max_message_length
}

output "max_request_length" {
  description = "returns a number"
  value       = fortios_webproxy_global.this.max_request_length
}

output "max_waf_body_cache_length" {
  description = "returns a number"
  value       = fortios_webproxy_global.this.max_waf_body_cache_length
}

output "ssl_ca_cert" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.ssl_ca_cert
}

output "ssl_cert" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.ssl_cert
}

output "strict_web_check" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.strict_web_check
}

output "tunnel_non_http" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.tunnel_non_http
}

output "unknown_http_version" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.unknown_http_version
}

output "webproxy_profile" {
  description = "returns a string"
  value       = fortios_webproxy_global.this.webproxy_profile
}

output "this" {
  value = fortios_webproxy_global.this
}
```

[top](#index)