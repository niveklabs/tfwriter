# ns1_zone

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_zone" {
  source = "./modules/ns1/d/ns1_zone"

  # additional_primaries - (optional) is a type of list of string
  additional_primaries = []
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "additional_primaries" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ns1_zone" "this" {
  additional_primaries = var.additional_primaries
  zone                 = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "dns_servers" {
  description = "returns a string"
  value       = data.ns1_zone.this.dns_servers
}

output "dnssec" {
  description = "returns a bool"
  value       = data.ns1_zone.this.dnssec
}

output "expiry" {
  description = "returns a number"
  value       = data.ns1_zone.this.expiry
}

output "hostmaster" {
  description = "returns a string"
  value       = data.ns1_zone.this.hostmaster
}

output "id" {
  description = "returns a string"
  value       = data.ns1_zone.this.id
}

output "link" {
  description = "returns a string"
  value       = data.ns1_zone.this.link
}

output "networks" {
  description = "returns a set of number"
  value       = data.ns1_zone.this.networks
}

output "nx_ttl" {
  description = "returns a number"
  value       = data.ns1_zone.this.nx_ttl
}

output "primary" {
  description = "returns a string"
  value       = data.ns1_zone.this.primary
}

output "refresh" {
  description = "returns a number"
  value       = data.ns1_zone.this.refresh
}

output "retry" {
  description = "returns a number"
  value       = data.ns1_zone.this.retry
}

output "secondaries" {
  description = "returns a set of object"
  value       = data.ns1_zone.this.secondaries
}

output "ttl" {
  description = "returns a number"
  value       = data.ns1_zone.this.ttl
}

output "this" {
  value = ns1_zone.this
}
```

[top](#index)