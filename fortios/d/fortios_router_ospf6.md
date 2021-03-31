# fortios_router_ospf6

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
module "fortios_router_ospf6" {
  source = "./modules/fortios/d/fortios_router_ospf6"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_ospf6" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "abr_type" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.abr_type
}

output "area" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf6.this.area
}

output "auto_cost_ref_bandwidth" {
  description = "returns a number"
  value       = data.fortios_router_ospf6.this.auto_cost_ref_bandwidth
}

output "bfd" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.bfd
}

output "default_information_metric" {
  description = "returns a number"
  value       = data.fortios_router_ospf6.this.default_information_metric
}

output "default_information_metric_type" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.default_information_metric_type
}

output "default_information_originate" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.default_information_originate
}

output "default_information_route_map" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.default_information_route_map
}

output "default_metric" {
  description = "returns a number"
  value       = data.fortios_router_ospf6.this.default_metric
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.id
}

output "log_neighbour_changes" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.log_neighbour_changes
}

output "ospf6_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf6.this.ospf6_interface
}

output "passive_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf6.this.passive_interface
}

output "redistribute" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf6.this.redistribute
}

output "router_id" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.router_id
}

output "spf_timers" {
  description = "returns a string"
  value       = data.fortios_router_ospf6.this.spf_timers
}

output "summary_address" {
  description = "returns a list of object"
  value       = data.fortios_router_ospf6.this.summary_address
}

output "this" {
  value = fortios_router_ospf6.this
}
```

[top](#index)