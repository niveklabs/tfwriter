# fortios_router_ripng

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
module "fortios_router_ripng" {
  source = "./modules/fortios/d/fortios_router_ripng"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_ripng" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "aggregate_address" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.aggregate_address
}

output "default_information_originate" {
  description = "returns a string"
  value       = data.fortios_router_ripng.this.default_information_originate
}

output "default_metric" {
  description = "returns a number"
  value       = data.fortios_router_ripng.this.default_metric
}

output "distance" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.distance
}

output "distribute_list" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.distribute_list
}

output "garbage_timer" {
  description = "returns a number"
  value       = data.fortios_router_ripng.this.garbage_timer
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_ripng.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.interface
}

output "max_out_metric" {
  description = "returns a number"
  value       = data.fortios_router_ripng.this.max_out_metric
}

output "neighbor" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.neighbor
}

output "network" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.network
}

output "offset_list" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.offset_list
}

output "passive_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.passive_interface
}

output "redistribute" {
  description = "returns a list of object"
  value       = data.fortios_router_ripng.this.redistribute
}

output "timeout_timer" {
  description = "returns a number"
  value       = data.fortios_router_ripng.this.timeout_timer
}

output "update_timer" {
  description = "returns a number"
  value       = data.fortios_router_ripng.this.update_timer
}

output "this" {
  value = fortios_router_ripng.this
}
```

[top](#index)