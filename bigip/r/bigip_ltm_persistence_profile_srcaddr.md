# bigip_ltm_persistence_profile_srcaddr

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
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_persistence_profile_srcaddr" {
  source = "./modules/bigip/r/bigip_ltm_persistence_profile_srcaddr"

  # app_service - (optional) is a type of string
  app_service = null
  # defaults_from - (required) is a type of string
  defaults_from = null
  # hash_algorithm - (optional) is a type of string
  hash_algorithm = null
  # map_proxies - (optional) is a type of string
  map_proxies = null
  # mask - (optional) is a type of string
  mask = null
  # match_across_pools - (optional) is a type of string
  match_across_pools = null
  # match_across_services - (optional) is a type of string
  match_across_services = null
  # match_across_virtuals - (optional) is a type of string
  match_across_virtuals = null
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
variable "app_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defaults_from" {
  description = "(required) - Inherit defaults from parent profile"
  type        = string
}

variable "hash_algorithm" {
  description = "(optional) - Specify the hash algorithm"
  type        = string
  default     = null
}

variable "map_proxies" {
  description = "(optional) - To enable _ disable directs all to the same single pool member"
  type        = string
  default     = null
}

variable "mask" {
  description = "(optional) - Identify a range of source IP addresses to manage together as a single source address affinity persistent connection when connecting to the pool. Must be a valid IPv4 or IPv6 mask."
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
  description = "(optional) - To enable _ disable match across services with given persistence record"
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
resource "bigip_ltm_persistence_profile_srcaddr" "this" {
  app_service           = var.app_service
  defaults_from         = var.defaults_from
  hash_algorithm        = var.hash_algorithm
  map_proxies           = var.map_proxies
  mask                  = var.mask
  match_across_pools    = var.match_across_pools
  match_across_services = var.match_across_services
  match_across_virtuals = var.match_across_virtuals
  mirror                = var.mirror
  name                  = var.name
  override_conn_limit   = var.override_conn_limit
  timeout               = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "app_service" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.app_service
}

output "hash_algorithm" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.hash_algorithm
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.id
}

output "map_proxies" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.map_proxies
}

output "mask" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.mask
}

output "match_across_pools" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.match_across_pools
}

output "match_across_services" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.match_across_services
}

output "match_across_virtuals" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.match_across_virtuals
}

output "mirror" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.mirror
}

output "override_conn_limit" {
  description = "returns a string"
  value       = bigip_ltm_persistence_profile_srcaddr.this.override_conn_limit
}

output "timeout" {
  description = "returns a number"
  value       = bigip_ltm_persistence_profile_srcaddr.this.timeout
}

output "this" {
  value = bigip_ltm_persistence_profile_srcaddr.this
}
```

[top](#index)