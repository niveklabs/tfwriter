# fortios_router_setting

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
module "fortios_router_setting" {
  source = "./modules/fortios/r/fortios_router_setting"

  # bgp_debug_flags - (optional) is a type of string
  bgp_debug_flags = null
  # hostname - (optional) is a type of string
  hostname = null
  # igmp_debug_flags - (optional) is a type of string
  igmp_debug_flags = null
  # imi_debug_flags - (optional) is a type of string
  imi_debug_flags = null
  # isis_debug_flags - (optional) is a type of string
  isis_debug_flags = null
  # ospf6_debug_events_flags - (optional) is a type of string
  ospf6_debug_events_flags = null
  # ospf6_debug_ifsm_flags - (optional) is a type of string
  ospf6_debug_ifsm_flags = null
  # ospf6_debug_lsa_flags - (optional) is a type of string
  ospf6_debug_lsa_flags = null
  # ospf6_debug_nfsm_flags - (optional) is a type of string
  ospf6_debug_nfsm_flags = null
  # ospf6_debug_nsm_flags - (optional) is a type of string
  ospf6_debug_nsm_flags = null
  # ospf6_debug_packet_flags - (optional) is a type of string
  ospf6_debug_packet_flags = null
  # ospf6_debug_route_flags - (optional) is a type of string
  ospf6_debug_route_flags = null
  # ospf_debug_events_flags - (optional) is a type of string
  ospf_debug_events_flags = null
  # ospf_debug_ifsm_flags - (optional) is a type of string
  ospf_debug_ifsm_flags = null
  # ospf_debug_lsa_flags - (optional) is a type of string
  ospf_debug_lsa_flags = null
  # ospf_debug_nfsm_flags - (optional) is a type of string
  ospf_debug_nfsm_flags = null
  # ospf_debug_nsm_flags - (optional) is a type of string
  ospf_debug_nsm_flags = null
  # ospf_debug_packet_flags - (optional) is a type of string
  ospf_debug_packet_flags = null
  # ospf_debug_route_flags - (optional) is a type of string
  ospf_debug_route_flags = null
  # pimdm_debug_flags - (optional) is a type of string
  pimdm_debug_flags = null
  # pimsm_debug_joinprune_flags - (optional) is a type of string
  pimsm_debug_joinprune_flags = null
  # pimsm_debug_simple_flags - (optional) is a type of string
  pimsm_debug_simple_flags = null
  # pimsm_debug_timer_flags - (optional) is a type of string
  pimsm_debug_timer_flags = null
  # rip_debug_flags - (optional) is a type of string
  rip_debug_flags = null
  # ripng_debug_flags - (optional) is a type of string
  ripng_debug_flags = null
  # show_filter - (optional) is a type of string
  show_filter = null
}
```

[top](#index)

### Variables

```terraform
variable "bgp_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "igmp_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "imi_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isis_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_events_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_ifsm_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_lsa_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_nfsm_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_nsm_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_packet_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf6_debug_route_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_events_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_ifsm_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_lsa_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_nfsm_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_nsm_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_packet_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ospf_debug_route_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pimdm_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pimsm_debug_joinprune_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pimsm_debug_simple_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pimsm_debug_timer_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rip_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ripng_debug_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "show_filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_setting" "this" {
  bgp_debug_flags             = var.bgp_debug_flags
  hostname                    = var.hostname
  igmp_debug_flags            = var.igmp_debug_flags
  imi_debug_flags             = var.imi_debug_flags
  isis_debug_flags            = var.isis_debug_flags
  ospf6_debug_events_flags    = var.ospf6_debug_events_flags
  ospf6_debug_ifsm_flags      = var.ospf6_debug_ifsm_flags
  ospf6_debug_lsa_flags       = var.ospf6_debug_lsa_flags
  ospf6_debug_nfsm_flags      = var.ospf6_debug_nfsm_flags
  ospf6_debug_nsm_flags       = var.ospf6_debug_nsm_flags
  ospf6_debug_packet_flags    = var.ospf6_debug_packet_flags
  ospf6_debug_route_flags     = var.ospf6_debug_route_flags
  ospf_debug_events_flags     = var.ospf_debug_events_flags
  ospf_debug_ifsm_flags       = var.ospf_debug_ifsm_flags
  ospf_debug_lsa_flags        = var.ospf_debug_lsa_flags
  ospf_debug_nfsm_flags       = var.ospf_debug_nfsm_flags
  ospf_debug_nsm_flags        = var.ospf_debug_nsm_flags
  ospf_debug_packet_flags     = var.ospf_debug_packet_flags
  ospf_debug_route_flags      = var.ospf_debug_route_flags
  pimdm_debug_flags           = var.pimdm_debug_flags
  pimsm_debug_joinprune_flags = var.pimsm_debug_joinprune_flags
  pimsm_debug_simple_flags    = var.pimsm_debug_simple_flags
  pimsm_debug_timer_flags     = var.pimsm_debug_timer_flags
  rip_debug_flags             = var.rip_debug_flags
  ripng_debug_flags           = var.ripng_debug_flags
  show_filter                 = var.show_filter
}
```

[top](#index)

### Outputs

```terraform
output "bgp_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.bgp_debug_flags
}

output "hostname" {
  description = "returns a string"
  value       = fortios_router_setting.this.hostname
}

output "id" {
  description = "returns a string"
  value       = fortios_router_setting.this.id
}

output "igmp_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.igmp_debug_flags
}

output "imi_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.imi_debug_flags
}

output "isis_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.isis_debug_flags
}

output "ospf6_debug_events_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_events_flags
}

output "ospf6_debug_ifsm_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_ifsm_flags
}

output "ospf6_debug_lsa_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_lsa_flags
}

output "ospf6_debug_nfsm_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_nfsm_flags
}

output "ospf6_debug_nsm_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_nsm_flags
}

output "ospf6_debug_packet_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_packet_flags
}

output "ospf6_debug_route_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf6_debug_route_flags
}

output "ospf_debug_events_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_events_flags
}

output "ospf_debug_ifsm_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_ifsm_flags
}

output "ospf_debug_lsa_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_lsa_flags
}

output "ospf_debug_nfsm_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_nfsm_flags
}

output "ospf_debug_nsm_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_nsm_flags
}

output "ospf_debug_packet_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_packet_flags
}

output "ospf_debug_route_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ospf_debug_route_flags
}

output "pimdm_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.pimdm_debug_flags
}

output "pimsm_debug_joinprune_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.pimsm_debug_joinprune_flags
}

output "pimsm_debug_simple_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.pimsm_debug_simple_flags
}

output "pimsm_debug_timer_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.pimsm_debug_timer_flags
}

output "rip_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.rip_debug_flags
}

output "ripng_debug_flags" {
  description = "returns a string"
  value       = fortios_router_setting.this.ripng_debug_flags
}

output "show_filter" {
  description = "returns a string"
  value       = fortios_router_setting.this.show_filter
}

output "this" {
  value = fortios_router_setting.this
}
```

[top](#index)