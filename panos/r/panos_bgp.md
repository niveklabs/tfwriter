# panos_bgp

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_bgp" {
  source = "./modules/panos/r/panos_bgp"

  # aggregate_med - (optional) is a type of bool
  aggregate_med = null
  # allow_redistribute_default_route - (optional) is a type of bool
  allow_redistribute_default_route = null
  # always_compare_med - (optional) is a type of bool
  always_compare_med = null
  # as_format - (optional) is a type of string
  as_format = null
  # as_number - (optional) is a type of string
  as_number = null
  # bfd_profile - (optional) is a type of string
  bfd_profile = null
  # confederation_member_as - (optional) is a type of string
  confederation_member_as = null
  # default_local_preference - (optional) is a type of string
  default_local_preference = null
  # deterministic_med_comparison - (optional) is a type of bool
  deterministic_med_comparison = null
  # ecmp_multi_as - (optional) is a type of bool
  ecmp_multi_as = null
  # enable - (optional) is a type of bool
  enable = null
  # enable_graceful_restart - (optional) is a type of bool
  enable_graceful_restart = null
  # enforce_first_as - (optional) is a type of bool
  enforce_first_as = null
  # install_route - (optional) is a type of bool
  install_route = null
  # local_restart_time - (optional) is a type of number
  local_restart_time = null
  # max_peer_restart_time - (optional) is a type of number
  max_peer_restart_time = null
  # reflector_cluster_id - (optional) is a type of string
  reflector_cluster_id = null
  # reject_default_route - (optional) is a type of bool
  reject_default_route = null
  # router_id - (optional) is a type of string
  router_id = null
  # stale_route_time - (optional) is a type of number
  stale_route_time = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "aggregate_med" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_redistribute_default_route" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "always_compare_med" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "as_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "as_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bfd_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "confederation_member_as" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_local_preference" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deterministic_med_comparison" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ecmp_multi_as" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_graceful_restart" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enforce_first_as" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "install_route" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "local_restart_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_peer_restart_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reflector_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reject_default_route" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "router_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stale_route_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_bgp" "this" {
  # aggregate_med - (optional) is a type of bool
  aggregate_med = var.aggregate_med
  # allow_redistribute_default_route - (optional) is a type of bool
  allow_redistribute_default_route = var.allow_redistribute_default_route
  # always_compare_med - (optional) is a type of bool
  always_compare_med = var.always_compare_med
  # as_format - (optional) is a type of string
  as_format = var.as_format
  # as_number - (optional) is a type of string
  as_number = var.as_number
  # bfd_profile - (optional) is a type of string
  bfd_profile = var.bfd_profile
  # confederation_member_as - (optional) is a type of string
  confederation_member_as = var.confederation_member_as
  # default_local_preference - (optional) is a type of string
  default_local_preference = var.default_local_preference
  # deterministic_med_comparison - (optional) is a type of bool
  deterministic_med_comparison = var.deterministic_med_comparison
  # ecmp_multi_as - (optional) is a type of bool
  ecmp_multi_as = var.ecmp_multi_as
  # enable - (optional) is a type of bool
  enable = var.enable
  # enable_graceful_restart - (optional) is a type of bool
  enable_graceful_restart = var.enable_graceful_restart
  # enforce_first_as - (optional) is a type of bool
  enforce_first_as = var.enforce_first_as
  # install_route - (optional) is a type of bool
  install_route = var.install_route
  # local_restart_time - (optional) is a type of number
  local_restart_time = var.local_restart_time
  # max_peer_restart_time - (optional) is a type of number
  max_peer_restart_time = var.max_peer_restart_time
  # reflector_cluster_id - (optional) is a type of string
  reflector_cluster_id = var.reflector_cluster_id
  # reject_default_route - (optional) is a type of bool
  reject_default_route = var.reject_default_route
  # router_id - (optional) is a type of string
  router_id = var.router_id
  # stale_route_time - (optional) is a type of number
  stale_route_time = var.stale_route_time
  # virtual_router - (required) is a type of string
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_bgp.this.id
}

output "this" {
  value = panos_bgp.this
}
```

[top](#index)