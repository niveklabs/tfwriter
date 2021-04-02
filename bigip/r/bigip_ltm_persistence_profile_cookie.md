# bigip_ltm_persistence_profile_cookie

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
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_persistence_profile_cookie" {
  source = "./modules/bigip/r/bigip_ltm_persistence_profile_cookie"

  # always_send - (optional) is a type of string
  always_send = null
  # app_service - (optional) is a type of string
  app_service = null
  # cookie_encryption - (optional) is a type of string
  cookie_encryption = null
  # cookie_encryption_passphrase - (optional) is a type of string
  cookie_encryption_passphrase = null
  # cookie_name - (optional) is a type of string
  cookie_name = null
  # defaults_from - (required) is a type of string
  defaults_from = null
  # expiration - (optional) is a type of string
  expiration = null
  # hash_length - (optional) is a type of number
  hash_length = null
  # hash_offset - (optional) is a type of number
  hash_offset = null
  # httponly - (optional) is a type of string
  httponly = null
  # match_across_pools - (optional) is a type of string
  match_across_pools = null
  # match_across_services - (optional) is a type of string
  match_across_services = null
  # match_across_virtuals - (optional) is a type of string
  match_across_virtuals = null
  # method - (optional) is a type of string
  method = null
  # mirror - (optional) is a type of string
  mirror = null
  # name - (required) is a type of string
  name = null
  # override_conn_limit - (optional) is a type of string
  override_conn_limit = null
  # timeout - (optional) is a type of number
  timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "always_send" {
  description = "(optional) - To enable _ disable always sending cookies"
  type        = string
  default     = null
}

variable "app_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cookie_encryption" {
  description = "(optional) - To required, preferred, or disabled policy for cookie encryption"
  type        = string
  default     = null
}

variable "cookie_encryption_passphrase" {
  description = "(optional) - Passphrase for encrypted cookies"
  type        = string
  default     = null
}

variable "cookie_name" {
  description = "(optional) - Name of the cookie to track persistence"
  type        = string
  default     = null
}

variable "defaults_from" {
  description = "(required) - Inherit defaults from parent profile"
  type        = string
}

variable "expiration" {
  description = "(optional) - Expiration TTL for cookie specified in D:H:M:S or in seconds"
  type        = string
  default     = null
}

variable "hash_length" {
  description = "(optional) - Length of hash to apply to cookie"
  type        = number
  default     = null
}

variable "hash_offset" {
  description = "(optional) - Number of characters to skip in the cookie for the hash"
  type        = number
  default     = null
}

variable "httponly" {
  description = "(optional) - To enable _ disable sending only over http"
  type        = string
  default     = null
}

variable "match_across_pools" {
  description = "(optional) - To enable _ disable match across pools with given persistence record"
  type        = string
  default     = null
}

variable "match_across_services" {
  description = "(optional) - To enable _ disable match across services with given persistence record"
  type        = string
  default     = null
}

variable "match_across_virtuals" {
  description = "(optional) - To enable _ disable match across virtual servers with given persistence record"
  type        = string
  default     = null
}

variable "method" {
  description = "(optional) - Specifies the type of cookie processing that the system uses"
  type        = string
  default     = null
}

variable "mirror" {
  description = "(optional) - To enable _ disable"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the persistence profile"
  type        = string
}

variable "override_conn_limit" {
  description = "(optional) - To enable _ disable that pool member connection limits are overridden for persisted clients. Per-virtual connection limits remain hard limits and are not overridden."
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional) - Timeout for persistence of the session"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_persistence_profile_cookie" "this" {
  always_send                  = var.always_send
  app_service                  = var.app_service
  cookie_encryption            = var.cookie_encryption
  cookie_encryption_passphrase = var.cookie_encryption_passphrase
  cookie_name                  = var.cookie_name
  defaults_from                = var.defaults_from
  expiration                   = var.expiration
  hash_length                  = var.hash_length
  hash_offset                  = var.hash_offset
  httponly                     = var.httponly
  match_across_pools           = var.match_across_pools
  match_across_services        = var.match_across_services
  match_across_virtuals        = var.match_across_virtuals
  method                       = var.method
  mirror                       = var.mirror
  name                         = var.name
  override_conn_limit          = var.override_conn_limit
  timeout                      = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "always_send" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.always_send
}

output "app_service" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.app_service
}

output "cookie_encryption" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.cookie_encryption
}

output "cookie_encryption_passphrase" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.cookie_encryption_passphrase
}

output "cookie_name" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.cookie_name
}

output "expiration" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.expiration
}

output "hash_length" {
  description = "returns a number"
  value       = bigip_ltm_persistence_profile_cookie.this.hash_length
}

output "hash_offset" {
  description = "returns a number"
  value       = bigip_ltm_persistence_profile_cookie.this.hash_offset
}

output "httponly" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.httponly
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.id
}

output "match_across_pools" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.match_across_pools
}

output "match_across_services" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.match_across_services
}

output "match_across_virtuals" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.match_across_virtuals
}

output "method" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.method
}

output "mirror" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.mirror
}

output "override_conn_limit" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_cookie.this.override_conn_limit
}

output "timeout" {
  description = "returns a number"
  value       = bigip_ltm_persistence_profile_cookie.this.timeout
}

output "this" {
  value = bigip_ltm_persistence_profile_cookie.this
}
```

[top](#index)