# fortios_router_ospf

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
module "fortios_router_ospf" {
  source = "./modules/fortios/d/fortios_router_ospf"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_ospf" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "abr_type" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.abr_type
}

output "area" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.area
}

output "auto_cost_ref_bandwidth" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.auto_cost_ref_bandwidth
}

output "bfd" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.bfd
}

output "database_overflow" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.database_overflow
}

output "database_overflow_max_lsas" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.database_overflow_max_lsas
}

output "database_overflow_time_to_recover" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.database_overflow_time_to_recover
}

output "default_information_metric" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.default_information_metric
}

output "default_information_metric_type" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.default_information_metric_type
}

output "default_information_originate" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.default_information_originate
}

output "default_information_route_map" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.default_information_route_map
}

output "default_metric" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.default_metric
}

output "distance" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.distance
}

output "distance_external" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.distance_external
}

output "distance_inter_area" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.distance_inter_area
}

output "distance_intra_area" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.distance_intra_area
}

output "distribute_list" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.distribute_list
}

output "distribute_list_in" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.distribute_list_in
}

output "distribute_route_map_in" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.distribute_route_map_in
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.id
}

output "log_neighbour_changes" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.log_neighbour_changes
}

output "neighbor" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.neighbor
}

output "network" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.network
}

output "ospf_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.ospf_interface
}

output "passive_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.passive_interface
}

output "redistribute" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.redistribute
}

output "restart_mode" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.restart_mode
}

output "restart_period" {
  description = "returns a number"
  value       = data.fortios_router_ospf.this.restart_period
}

output "rfc1583_compatible" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.rfc1583_compatible
}

output "router_id" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.router_id
}

output "spf_timers" {
  description = "returns a string"
  value       = data.fortios_router_ospf.this.spf_timers
}

output "summary_address" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf.this.summary_address
}

output "this" {
  value = fortios_router_ospf.this
}
```

[top](#index)