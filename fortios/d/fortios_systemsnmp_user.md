# fortios_systemsnmp_user

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
module "fortios_systemsnmp_user" {
  source = "./modules/fortios/d/fortios_systemsnmp_user"

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
data "fortios_systemsnmp_user" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "auth_proto" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.auth_proto
}

output "auth_pwd" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.auth_pwd
  sensitive   = true
}

output "events" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.events
}

output "ha_direct" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.ha_direct
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.id
}

output "notify_hosts" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.notify_hosts
}

output "notify_hosts6" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.notify_hosts6
}

output "priv_proto" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.priv_proto
}

output "priv_pwd" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.priv_pwd
  sensitive   = true
}

output "queries" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.queries
}

output "query_port" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_user.this.query_port
}

output "security_level" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.security_level
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.source_ip
}

output "source_ipv6" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.source_ipv6
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.status
}

output "trap_lport" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_user.this.trap_lport
}

output "trap_rport" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_user.this.trap_rport
}

output "trap_status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_user.this.trap_status
}

output "this" {
  value = fortios_systemsnmp_user.this
}
```

[top](#index)