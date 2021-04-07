# fortios_firewallshaper_trafficshaper

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
module "fortios_firewallshaper_trafficshaper" {
  source = "./modules/fortios/d/fortios_firewallshaper_trafficshaper"

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
data "fortios_firewallshaper_trafficshaper" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_unit" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.bandwidth_unit
}

output "diffserv" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.diffserv
}

output "diffservcode" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.diffservcode
}

output "dscp_marking_method" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.dscp_marking_method
}

output "exceed_bandwidth" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_trafficshaper.this.exceed_bandwidth
}

output "exceed_class_id" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_trafficshaper.this.exceed_class_id
}

output "exceed_dscp" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.exceed_dscp
}

output "guaranteed_bandwidth" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_trafficshaper.this.guaranteed_bandwidth
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.id
}

output "maximum_bandwidth" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_trafficshaper.this.maximum_bandwidth
}

output "maximum_dscp" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.maximum_dscp
}

output "overhead" {
  description = "returns a number"
  value       = data.fortios_firewallshaper_trafficshaper.this.overhead
}

output "per_policy" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.per_policy
}

output "priority" {
  description = "returns a string"
  value       = data.fortios_firewallshaper_trafficshaper.this.priority
}

output "this" {
  value = fortios_firewallshaper_trafficshaper.this
}
```

[top](#index)