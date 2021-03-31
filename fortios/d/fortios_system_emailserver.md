# fortios_system_emailserver

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
module "fortios_system_emailserver" {
  source = "./modules/fortios/d/fortios_system_emailserver"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_emailserver" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "authenticate" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.authenticate
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.id
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = data.fortios_system_emailserver.this.port
}

output "reply_to" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.reply_to
}

output "security" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.security
}

output "server" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.source_ip6
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.ssl_min_proto_version
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.type
}

output "username" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.username
}

output "validate_server" {
  description = "returns a string"
  value       = data.fortios_system_emailserver.this.validate_server
}

output "this" {
  value = fortios_system_emailserver.this
}
```

[top](#index)