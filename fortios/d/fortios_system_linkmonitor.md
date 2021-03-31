# fortios_system_linkmonitor

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
module "fortios_system_linkmonitor" {
  source = "./modules/fortios/d/fortios_system_linkmonitor"

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
data "fortios_system_linkmonitor" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "addr_mode" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.addr_mode
}

output "failtime" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.failtime
}

output "gateway_ip" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.gateway_ip
}

output "gateway_ip6" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.gateway_ip6
}

output "ha_priority" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.ha_priority
}

output "http_agent" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.http_agent
}

output "http_get" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.http_get
}

output "http_match" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.http_match
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.id
}

output "interval" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.interval
}

output "packet_size" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.packet_size
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.port
}

output "probe_count" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.probe_count
}

output "probe_timeout" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.probe_timeout
}

output "protocol" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.protocol
}

output "recoverytime" {
  description = "returns a number"
  value       = data.fortios_system_linkmonitor.this.recoverytime
}

output "security_mode" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.security_mode
}

output "server" {
  description = "returns a list of object"
  value       = data.fortios_system_linkmonitor.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.source_ip6
}

output "srcintf" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.srcintf
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.status
}

output "update_cascade_interface" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.update_cascade_interface
}

output "update_static_route" {
  description = "returns a string"
  value       = data.fortios_system_linkmonitor.this.update_static_route
}

output "this" {
  value = fortios_system_linkmonitor.this
}
```

[top](#index)