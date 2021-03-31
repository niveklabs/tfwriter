# fortios_router_multicast

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
module "fortios_router_multicast" {
  source = "./modules/fortios/d/fortios_router_multicast"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_multicast" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_router_multicast.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = data.fortios_router_multicast.this.interface
}

output "multicast_routing" {
  description = "returns a string"
  value       = data.fortios_router_multicast.this.multicast_routing
}

output "pim_sm_global" {
  description = "returns a list of object"
  value       = data.fortios_router_multicast.this.pim_sm_global
}

output "route_limit" {
  description = "returns a number"
  value       = data.fortios_router_multicast.this.route_limit
}

output "route_threshold" {
  description = "returns a number"
  value       = data.fortios_router_multicast.this.route_threshold
}

output "this" {
  value = fortios_router_multicast.this
}
```

[top](#index)