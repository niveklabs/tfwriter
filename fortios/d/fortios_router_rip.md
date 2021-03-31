# fortios_router_rip

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
module "fortios_router_rip" {
  source = "./modules/fortios/d/fortios_router_rip"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_rip" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "default_information_originate" {
  description = "returns a string"
  value       = data.fortios_router_rip.this.default_information_originate
}

output "default_metric" {
  description = "returns a number"
  value       = data.fortios_router_rip.this.default_metric
}

output "distance" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.distance
}

output "distribute_list" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.distribute_list
}

output "garbage_timer" {
  description = "returns a number"
  value       = data.fortios_router_rip.this.garbage_timer
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_rip.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.interface
}

output "max_out_metric" {
  description = "returns a number"
  value       = data.fortios_router_rip.this.max_out_metric
}

output "neighbor" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.neighbor
}

output "network" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.network
}

output "offset_list" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.offset_list
}

output "passive_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.passive_interface
}

output "recv_buffer_size" {
  description = "returns a number"
  value       = data.fortios_router_rip.this.recv_buffer_size
}

output "redistribute" {
  description = "returns a list of object"
  value       = data.fortios_router_rip.this.redistribute
}

output "timeout_timer" {
  description = "returns a number"
  value       = data.fortios_router_rip.this.timeout_timer
}

output "update_timer" {
  description = "returns a number"
  value       = data.fortios_router_rip.this.update_timer
}

output "version" {
  description = "returns a string"
  value       = data.fortios_router_rip.this.version
}

output "this" {
  value = fortios_router_rip.this
}
```

[top](#index)