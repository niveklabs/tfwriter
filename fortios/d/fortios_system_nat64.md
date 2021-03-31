# fortios_system_nat64

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
module "fortios_system_nat64" {
  source = "./modules/fortios/d/fortios_system_nat64"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_nat64" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "always_synthesize_aaaa_record" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.always_synthesize_aaaa_record
}

output "generate_ipv6_fragment_header" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.generate_ipv6_fragment_header
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.id
}

output "nat46_force_ipv4_packet_forwarding" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.nat46_force_ipv4_packet_forwarding
}

output "nat64_prefix" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.nat64_prefix
}

output "secondary_prefix" {
  description = "returns a list of object"
  value       = data.fortios_system_nat64.this.secondary_prefix
}

output "secondary_prefix_status" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.secondary_prefix_status
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_nat64.this.status
}

output "this" {
  value = fortios_system_nat64.this
}
```

[top](#index)