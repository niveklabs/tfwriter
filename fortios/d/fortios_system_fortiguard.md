# fortios_system_fortiguard

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
module "fortios_system_fortiguard" {
  source = "./modules/fortios/d/fortios_system_fortiguard"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_fortiguard" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "antispam_cache" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.antispam_cache
}

output "antispam_cache_mpercent" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.antispam_cache_mpercent
}

output "antispam_cache_ttl" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.antispam_cache_ttl
}

output "antispam_expiration" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.antispam_expiration
}

output "antispam_force_off" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.antispam_force_off
}

output "antispam_license" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.antispam_license
}

output "antispam_timeout" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.antispam_timeout
}

output "anycast_sdns_server_ip" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.anycast_sdns_server_ip
}

output "anycast_sdns_server_port" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.anycast_sdns_server_port
}

output "auto_join_forticloud" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.auto_join_forticloud
}

output "ddns_server_ip" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.ddns_server_ip
}

output "ddns_server_port" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.ddns_server_port
}

output "fortiguard_anycast" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.fortiguard_anycast
}

output "fortiguard_anycast_source" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.fortiguard_anycast_source
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.interface_select_method
}

output "load_balance_servers" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.load_balance_servers
}

output "outbreak_prevention_cache" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_cache
}

output "outbreak_prevention_cache_mpercent" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_cache_mpercent
}

output "outbreak_prevention_cache_ttl" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_cache_ttl
}

output "outbreak_prevention_expiration" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_expiration
}

output "outbreak_prevention_force_off" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_force_off
}

output "outbreak_prevention_license" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_license
}

output "outbreak_prevention_timeout" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.outbreak_prevention_timeout
}

output "port" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.protocol
}

output "proxy_password" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.proxy_password
  sensitive   = true
}

output "proxy_server_ip" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.proxy_server_ip
}

output "proxy_server_port" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.proxy_server_port
}

output "proxy_username" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.proxy_username
}

output "sandbox_region" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.sandbox_region
}

output "sdns_options" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.sdns_options
}

output "sdns_server_ip" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.sdns_server_ip
}

output "sdns_server_port" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.sdns_server_port
}

output "service_account_id" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.service_account_id
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.source_ip6
}

output "update_server_location" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.update_server_location
}

output "webfilter_cache" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.webfilter_cache
}

output "webfilter_cache_ttl" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.webfilter_cache_ttl
}

output "webfilter_expiration" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.webfilter_expiration
}

output "webfilter_force_off" {
  description = "returns a string"
  value       = data.fortios_system_fortiguard.this.webfilter_force_off
}

output "webfilter_license" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.webfilter_license
}

output "webfilter_timeout" {
  description = "returns a number"
  value       = data.fortios_system_fortiguard.this.webfilter_timeout
}

output "this" {
  value = fortios_system_fortiguard.this
}
```

[top](#index)