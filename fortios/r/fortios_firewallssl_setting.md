# fortios_firewallssl_setting

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
module "fortios_firewallssl_setting" {
  source = "./modules/fortios/r/fortios_firewallssl_setting"

  # abbreviate_handshake - (optional) is a type of string
  abbreviate_handshake = null
  # cert_cache_capacity - (required) is a type of number
  cert_cache_capacity = null
  # cert_cache_timeout - (required) is a type of number
  cert_cache_timeout = null
  # kxp_queue_threshold - (optional) is a type of number
  kxp_queue_threshold = null
  # no_matching_cipher_action - (required) is a type of string
  no_matching_cipher_action = null
  # proxy_connect_timeout - (required) is a type of number
  proxy_connect_timeout = null
  # session_cache_capacity - (required) is a type of number
  session_cache_capacity = null
  # session_cache_timeout - (required) is a type of number
  session_cache_timeout = null
  # ssl_dh_bits - (required) is a type of string
  ssl_dh_bits = null
  # ssl_queue_threshold - (optional) is a type of number
  ssl_queue_threshold = null
  # ssl_send_empty_frags - (required) is a type of string
  ssl_send_empty_frags = null
}
```

[top](#index)

### Variables

```terraform
variable "abbreviate_handshake" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_cache_capacity" {
  description = "(required)"
  type        = number
}

variable "cert_cache_timeout" {
  description = "(required)"
  type        = number
}

variable "kxp_queue_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "no_matching_cipher_action" {
  description = "(required)"
  type        = string
}

variable "proxy_connect_timeout" {
  description = "(required)"
  type        = number
}

variable "session_cache_capacity" {
  description = "(required)"
  type        = number
}

variable "session_cache_timeout" {
  description = "(required)"
  type        = number
}

variable "ssl_dh_bits" {
  description = "(required)"
  type        = string
}

variable "ssl_queue_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_send_empty_frags" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallssl_setting" "this" {
  abbreviate_handshake      = var.abbreviate_handshake
  cert_cache_capacity       = var.cert_cache_capacity
  cert_cache_timeout        = var.cert_cache_timeout
  kxp_queue_threshold       = var.kxp_queue_threshold
  no_matching_cipher_action = var.no_matching_cipher_action
  proxy_connect_timeout     = var.proxy_connect_timeout
  session_cache_capacity    = var.session_cache_capacity
  session_cache_timeout     = var.session_cache_timeout
  ssl_dh_bits               = var.ssl_dh_bits
  ssl_queue_threshold       = var.ssl_queue_threshold
  ssl_send_empty_frags      = var.ssl_send_empty_frags
}
```

[top](#index)

### Outputs

```terraform
output "abbreviate_handshake" {
  description = "returns a string"
  value       = fortios_firewallssl_setting.this.abbreviate_handshake
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallssl_setting.this.id
}

output "kxp_queue_threshold" {
  description = "returns a number"
  value       = fortios_firewallssl_setting.this.kxp_queue_threshold
}

output "ssl_queue_threshold" {
  description = "returns a number"
  value       = fortios_firewallssl_setting.this.ssl_queue_threshold
}

output "this" {
  value = fortios_firewallssl_setting.this
}
```

[top](#index)