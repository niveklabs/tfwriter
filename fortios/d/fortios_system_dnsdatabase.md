# fortios_system_dnsdatabase

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
module "fortios_system_dnsdatabase" {
  source = "./modules/fortios/d/fortios_system_dnsdatabase"

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
data "fortios_system_dnsdatabase" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "allow_transfer" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.allow_transfer
}

output "authoritative" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.authoritative
}

output "contact" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.contact
}

output "dns_entry" {
  description = "returns a list of object"
  value       = data.fortios_system_dnsdatabase.this.dns_entry
}

output "domain" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.domain
}

output "forwarder" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.forwarder
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.id
}

output "ip_master" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.ip_master
}

output "ip_primary" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.ip_primary
}

output "primary_name" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.primary_name
}

output "rr_max" {
  description = "returns a number"
  value       = data.fortios_system_dnsdatabase.this.rr_max
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.source_ip
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.status
}

output "ttl" {
  description = "returns a number"
  value       = data.fortios_system_dnsdatabase.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.type
}

output "view" {
  description = "returns a string"
  value       = data.fortios_system_dnsdatabase.this.view
}

output "this" {
  value = fortios_system_dnsdatabase.this
}
```

[top](#index)