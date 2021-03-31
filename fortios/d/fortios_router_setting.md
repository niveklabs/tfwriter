# fortios_router_setting

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_router_setting"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_setting" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "bgp_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.bgp_debug_flags
}

output "hostname" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.id
}

output "igmp_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.igmp_debug_flags
}

output "imi_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.imi_debug_flags
}

output "isis_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.isis_debug_flags
}

output "ospf6_debug_events_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_events_flags
}

output "ospf6_debug_ifsm_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_ifsm_flags
}

output "ospf6_debug_lsa_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_lsa_flags
}

output "ospf6_debug_nfsm_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_nfsm_flags
}

output "ospf6_debug_nsm_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_nsm_flags
}

output "ospf6_debug_packet_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_packet_flags
}

output "ospf6_debug_route_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf6_debug_route_flags
}

output "ospf_debug_events_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_events_flags
}

output "ospf_debug_ifsm_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_ifsm_flags
}

output "ospf_debug_lsa_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_lsa_flags
}

output "ospf_debug_nfsm_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_nfsm_flags
}

output "ospf_debug_nsm_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_nsm_flags
}

output "ospf_debug_packet_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_packet_flags
}

output "ospf_debug_route_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ospf_debug_route_flags
}

output "pimdm_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.pimdm_debug_flags
}

output "pimsm_debug_joinprune_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.pimsm_debug_joinprune_flags
}

output "pimsm_debug_simple_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.pimsm_debug_simple_flags
}

output "pimsm_debug_timer_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.pimsm_debug_timer_flags
}

output "rip_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.rip_debug_flags
}

output "ripng_debug_flags" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.ripng_debug_flags
}

output "show_filter" {
  description = "returns a string"
  value       = data.fortios_router_setting.this.show_filter
}

output "this" {
  value = fortios_router_setting.this
}
```

[top](#index)