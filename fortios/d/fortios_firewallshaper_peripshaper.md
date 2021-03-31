# fortios_firewallshaper_peripshaper

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
module "fortios_firewallshaper_peripshaper" {
  source = "./modules/fortios/d/fortios_firewallshaper_peripshaper"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_firewallshaper_peripshaper" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_unit" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_peripshaper.this.bandwidth_unit
}

output "diffserv_forward" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_peripshaper.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_peripshaper.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_peripshaper.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_peripshaper.this.diffservcode_rev
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_peripshaper.this.id
}

output "max_bandwidth" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_peripshaper.this.max_bandwidth
}

output "max_concurrent_session" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_peripshaper.this.max_concurrent_session
}

output "max_concurrent_tcp_session" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_peripshaper.this.max_concurrent_tcp_session
}

output "max_concurrent_udp_session" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_peripshaper.this.max_concurrent_udp_session
}

output "this" {
  value = fortios_firewallshaper_peripshaper.this
}
```

[top](#index)