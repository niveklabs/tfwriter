# fortios_system_pppoeinterface

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
module "fortios_system_pppoeinterface" {
  source = "./modules/fortios/d/fortios_system_pppoeinterface"

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
data "fortios_system_pppoeinterface" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "ac_name" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.ac_name
}

output "auth_type" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.auth_type
}

output "device" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.device
}

output "dial_on_demand" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.dial_on_demand
}

output "disc_retry_timeout" {
  description = "returns a number"
  value       = data.fortios_system_pppoeinterface.this.disc_retry_timeout
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.id
}

output "idle_timeout" {
  description = "returns a number"
  value       = data.fortios_system_pppoeinterface.this.idle_timeout
}

output "ipunnumbered" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.ipunnumbered
}

output "ipv6" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.ipv6
}

output "lcp_echo_interval" {
  description = "returns a number"
  value       = data.fortios_system_pppoeinterface.this.lcp_echo_interval
}

output "lcp_max_echo_fails" {
  description = "returns a number"
  value       = data.fortios_system_pppoeinterface.this.lcp_max_echo_fails
}

output "padt_retry_timeout" {
  description = "returns a number"
  value       = data.fortios_system_pppoeinterface.this.padt_retry_timeout
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.password
  sensitive   = true
}

output "pppoe_unnumbered_negotiate" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.pppoe_unnumbered_negotiate
}

output "service_name" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.service_name
}

output "username" {
  description = "returns a string"
  value       = data.fortios_system_pppoeinterface.this.username
}

output "this" {
  value = fortios_system_pppoeinterface.this
}
```

[top](#index)