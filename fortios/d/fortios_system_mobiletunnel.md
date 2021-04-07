# fortios_system_mobiletunnel

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
module "fortios_system_mobiletunnel" {
  source = "./modules/fortios/d/fortios_system_mobiletunnel"

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
data "fortios_system_mobiletunnel" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "hash_algorithm" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.hash_algorithm
}

output "home_address" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.home_address
}

output "home_agent" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.home_agent
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.id
}

output "lifetime" {
  description = "returns a number"
  value       = data.fortios_system_mobiletunnel.this.lifetime
}

output "n_mhae_key" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.n_mhae_key
  sensitive   = true
}

output "n_mhae_key_type" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.n_mhae_key_type
}

output "n_mhae_spi" {
  description = "returns a number"
  value       = data.fortios_system_mobiletunnel.this.n_mhae_spi
}

output "network" {
  description = "returns a list of object"
  value       = data.fortios_system_mobiletunnel.this.network
}

output "reg_interval" {
  description = "returns a number"
  value       = data.fortios_system_mobiletunnel.this.reg_interval
}

output "reg_retry" {
  description = "returns a number"
  value       = data.fortios_system_mobiletunnel.this.reg_retry
}

output "renew_interval" {
  description = "returns a number"
  value       = data.fortios_system_mobiletunnel.this.renew_interval
}

output "roaming_interface" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.roaming_interface
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.status
}

output "tunnel_mode" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnel.this.tunnel_mode
}

output "this" {
  value = fortios_system_mobiletunnel.this
}
```

[top](#index)