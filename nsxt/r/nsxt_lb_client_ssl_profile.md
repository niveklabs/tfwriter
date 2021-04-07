# nsxt_lb_client_ssl_profile

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_lb_client_ssl_profile" {
  source = "./modules/nsxt/r/nsxt_lb_client_ssl_profile"

  # ciphers - (optional) is a type of set of string
  ciphers = []
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # prefer_server_ciphers - (optional) is a type of bool
  prefer_server_ciphers = null
  # protocols - (optional) is a type of set of string
  protocols = []
  # session_cache_enabled - (optional) is a type of bool
  session_cache_enabled = null
  # session_cache_timeout - (optional) is a type of number
  session_cache_timeout = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ciphers" {
  description = "(optional) - Supported SSL cipher list"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "prefer_server_ciphers" {
  description = "(optional) - Allow server to override the client's preference"
  type        = bool
  default     = null
}

variable "protocols" {
  description = "(optional) - SSL versions TLS1.1 and TLS1.2 are supported and enabled by default. SSLv2, SSLv3, and TLS1.0 are supported, but disabled by default"
  type        = set(string)
  default     = null
}

variable "session_cache_enabled" {
  description = "(optional) - Reuse previously negotiated security parameters during handshake"
  type        = bool
  default     = null
}

variable "session_cache_timeout" {
  description = "(optional) - For how long the SSL session parameters can be reused"
  type        = number
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_lb_client_ssl_profile" "this" {
  # ciphers - (optional) is a type of set of string
  ciphers = var.ciphers
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # prefer_server_ciphers - (optional) is a type of bool
  prefer_server_ciphers = var.prefer_server_ciphers
  # protocols - (optional) is a type of set of string
  protocols = var.protocols
  # session_cache_enabled - (optional) is a type of bool
  session_cache_enabled = var.session_cache_enabled
  # session_cache_timeout - (optional) is a type of number
  session_cache_timeout = var.session_cache_timeout

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ciphers" {
  description = "returns a set of string"
  value       = nsxt_lb_client_ssl_profile.this.ciphers
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_client_ssl_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_client_ssl_profile.this.id
}

output "is_secure" {
  description = "returns a bool"
  value       = nsxt_lb_client_ssl_profile.this.is_secure
}

output "protocols" {
  description = "returns a set of string"
  value       = nsxt_lb_client_ssl_profile.this.protocols
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_client_ssl_profile.this.revision
}

output "this" {
  value = nsxt_lb_client_ssl_profile.this
}
```

[top](#index)