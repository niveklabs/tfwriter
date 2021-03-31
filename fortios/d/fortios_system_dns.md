# fortios_system_dns

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
module "fortios_system_dns" {
  source = "./modules/fortios/d/fortios_system_dns"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_dns" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "cache_notfound_responses" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.cache_notfound_responses
}

output "dns_cache_limit" {
  description = "returns a number"
  value       = data.fortios_system_dns.this.dns_cache_limit
}

output "dns_cache_ttl" {
  description = "returns a number"
  value       = data.fortios_system_dns.this.dns_cache_ttl
}

output "dns_over_tls" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.dns_over_tls
}

output "domain" {
  description = "returns a list of object"
  value       = data.fortios_system_dns.this.domain
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.interface_select_method
}

output "ip6_primary" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.ip6_primary
}

output "ip6_secondary" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.ip6_secondary
}

output "primary" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.primary
}

output "retry" {
  description = "returns a number"
  value       = data.fortios_system_dns.this.retry
}

output "secondary" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.secondary
}

output "server_hostname" {
  description = "returns a list of object"
  value       = data.fortios_system_dns.this.server_hostname
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.source_ip
}

output "ssl_certificate" {
  description = "returns a string"
  value       = data.fortios_system_dns.this.ssl_certificate
}

output "timeout" {
  description = "returns a number"
  value       = data.fortios_system_dns.this.timeout
}

output "this" {
  value = fortios_system_dns.this
}
```

[top](#index)