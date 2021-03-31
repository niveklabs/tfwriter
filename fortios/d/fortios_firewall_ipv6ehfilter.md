# fortios_firewall_ipv6ehfilter

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
module "fortios_firewall_ipv6ehfilter" {
  source = "./modules/fortios/d/fortios_firewall_ipv6ehfilter"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_firewall_ipv6ehfilter" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "auth" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.auth
}

output "dest_opt" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.dest_opt
}

output "fragment" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.fragment
}

output "hdopt_type" {
  description = "returns a number"
  value       = data.fortios_firewall_ipv6ehfilter.this.hdopt_type
}

output "hop_opt" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.hop_opt
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.id
}

output "no_next" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.no_next
}

output "routing" {
  description = "returns a string"
  value       = data.fortios_firewall_ipv6ehfilter.this.routing
}

output "routing_type" {
  description = "returns a number"
  value       = data.fortios_firewall_ipv6ehfilter.this.routing_type
}

output "this" {
  value = fortios_firewall_ipv6ehfilter.this
}
```

[top](#index)