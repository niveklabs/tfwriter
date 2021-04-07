# fortios_router_static6

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
module "fortios_router_static6" {
  source = "./modules/fortios/d/fortios_router_static6"

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
data "fortios_router_static6" "this" {
  # seq_num - (required) is a type of number
  seq_num = var.seq_num
}
```

[top](#index)

### Outputs

```terraform
output "bfd" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.bfd
}

output "blackhole" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.blackhole
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.comment
}

output "device" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.device
}

output "devindex" {
  description = "returns a number"
  value       = data.fortios_router_static6.this.devindex
}

output "distance" {
  description = "returns a number"
  value       = data.fortios_router_static6.this.distance
}

output "dst" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.dst
}

output "gateway" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.id
}

output "link_monitor_exempt" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.link_monitor_exempt
}

output "priority" {
  description = "returns a number"
  value       = data.fortios_router_static6.this.priority
}

output "sdwan" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.sdwan
}

output "status" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.status
}

output "virtual_wan_link" {
  description = "returns a string"
  value       = data.fortios_router_static6.this.virtual_wan_link
}

output "this" {
  value = fortios_router_static6.this
}
```

[top](#index)