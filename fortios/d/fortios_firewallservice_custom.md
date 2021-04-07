# fortios_firewallservice_custom

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
module "fortios_firewallservice_custom" {
  source = "./modules/fortios/d/fortios_firewallservice_custom"

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
data "fortios_firewallservice_custom" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "app_category" {
  description = "returns a list of object"
  value       = data.fortios_firewallservice_custom.this.app_category
}

output "app_service_type" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.app_service_type
}

output "application" {
  description = "returns a list of object"
  value       = data.fortios_firewallservice_custom.this.application
}

output "category" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.category
}

output "check_reset_range" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.check_reset_range
}

output "color" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.comment
}

output "fqdn" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.fqdn
}

output "helper" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.helper
}

output "icmpcode" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.icmpcode
}

output "icmptype" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.icmptype
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.id
}

output "iprange" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.iprange
}

output "protocol" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.protocol
}

output "protocol_number" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.protocol_number
}

output "proxy" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.proxy
}

output "sctp_portrange" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.sctp_portrange
}

output "session_ttl" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.session_ttl
}

output "tcp_halfclose_timer" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.tcp_halfclose_timer
}

output "tcp_halfopen_timer" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.tcp_halfopen_timer
}

output "tcp_portrange" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.tcp_portrange
}

output "tcp_timewait_timer" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.tcp_timewait_timer
}

output "udp_idle_timer" {
  description = "returns a number"
  value       = data.fortios_firewallservice_custom.this.udp_idle_timer
}

output "udp_portrange" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.udp_portrange
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewallservice_custom.this.visibility
}

output "this" {
  value = fortios_firewallservice_custom.this
}
```

[top](#index)