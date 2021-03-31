# fortios_system_resourcelimits

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
module "fortios_system_resourcelimits" {
  source = "./modules/fortios/d/fortios_system_resourcelimits"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_resourcelimits" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "custom_service" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.custom_service
}

output "dialup_tunnel" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.dialup_tunnel
}

output "firewall_address" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.firewall_address
}

output "firewall_addrgrp" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.firewall_addrgrp
}

output "firewall_policy" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.firewall_policy
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_resourcelimits.this.id
}

output "ipsec_phase1" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.ipsec_phase1
}

output "ipsec_phase1_interface" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.ipsec_phase1_interface
}

output "ipsec_phase2" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.ipsec_phase2
}

output "ipsec_phase2_interface" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.ipsec_phase2_interface
}

output "log_disk_quota" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.log_disk_quota
}

output "onetime_schedule" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.onetime_schedule
}

output "proxy" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.proxy
}

output "recurring_schedule" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.recurring_schedule
}

output "service_group" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.service_group
}

output "session" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.session
}

output "sslvpn" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.sslvpn
}

output "user" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.user
}

output "user_group" {
  description = "returns a number"
  value       = data.fortios_system_resourcelimits.this.user_group
}

output "this" {
  value = fortios_system_resourcelimits.this
}
```

[top](#index)