# fortios_router_multicast6

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
module "fortios_router_multicast6" {
  source = "./modules/fortios/d/fortios_router_multicast6"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_multicast6" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_router_multicast6.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = data.fortios_router_multicast6.this.interface
}

output "multicast_pmtu" {
  description = "returns a string"
  value       = data.fortios_router_multicast6.this.multicast_pmtu
}

output "multicast_routing" {
  description = "returns a string"
  value       = data.fortios_router_multicast6.this.multicast_routing
}

output "pim_sm_global" {
  description = "returns a list of object"
  value       = data.fortios_router_multicast6.this.pim_sm_global
}

output "this" {
  value = fortios_router_multicast6.this
}
```

[top](#index)