# fortios_router_static

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
module "fortios_router_static" {
  source = "./modules/fortios/d/fortios_router_static"

  # seq_num - (required) is a type of number
  seq_num = null
}
```

[top](#index)

### Variables

```terraform
variable "seq_num" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_router_static" "this" {
  seq_num = var.seq_num
}
```

[top](#index)

### Outputs

```terraform
output "bfd" {
  description = "returns a string"
  value       = data.fortios_router_static.this.bfd
}

output "blackhole" {
  description = "returns a string"
  value       = data.fortios_router_static.this.blackhole
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_router_static.this.comment
}

output "device" {
  description = "returns a string"
  value       = data.fortios_router_static.this.device
}

output "distance" {
  description = "returns a number"
  value       = data.fortios_router_static.this.distance
}

output "dst" {
  description = "returns a string"
  value       = data.fortios_router_static.this.dst
}

output "dstaddr" {
  description = "returns a string"
  value       = data.fortios_router_static.this.dstaddr
}

output "dynamic_gateway" {
  description = "returns a string"
  value       = data.fortios_router_static.this.dynamic_gateway
}

output "gateway" {
  description = "returns a string"
  value       = data.fortios_router_static.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_static.this.id
}

output "internet_service" {
  description = "returns a number"
  value       = data.fortios_router_static.this.internet_service
}

output "internet_service_custom" {
  description = "returns a string"
  value       = data.fortios_router_static.this.internet_service_custom
}

output "link_monitor_exempt" {
  description = "returns a string"
  value       = data.fortios_router_static.this.link_monitor_exempt
}

output "priority" {
  description = "returns a number"
  value       = data.fortios_router_static.this.priority
}

output "sdwan" {
  description = "returns a string"
  value       = data.fortios_router_static.this.sdwan
}

output "src" {
  description = "returns a string"
  value       = data.fortios_router_static.this.src
}

output "status" {
  description = "returns a string"
  value       = data.fortios_router_static.this.status
}

output "virtual_wan_link" {
  description = "returns a string"
  value       = data.fortios_router_static.this.virtual_wan_link
}

output "vrf" {
  description = "returns a number"
  value       = data.fortios_router_static.this.vrf
}

output "weight" {
  description = "returns a number"
  value       = data.fortios_router_static.this.weight
}

output "this" {
  value = fortios_router_static.this
}
```

[top](#index)