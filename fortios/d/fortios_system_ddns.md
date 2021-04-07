# fortios_system_ddns

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
module "fortios_system_ddns" {
  source = "./modules/fortios/d/fortios_system_ddns"

  # ddnsid - (required) is a type of number
  ddnsid = null
}
```

[top](#index)

### Variables

```terraform
variable "ddnsid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_ddns" "this" {
  # ddnsid - (required) is a type of number
  ddnsid = var.ddnsid
}
```

[top](#index)

### Outputs

```terraform
output "bound_ip" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.bound_ip
}

output "clear_text" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.clear_text
}

output "ddns_auth" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_auth
}

output "ddns_domain" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_domain
}

output "ddns_key" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_key
  sensitive   = true
}

output "ddns_keyname" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_keyname
}

output "ddns_password" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_password
  sensitive   = true
}

output "ddns_server" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_server
}

output "ddns_server_ip" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_server_ip
}

output "ddns_sn" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_sn
}

output "ddns_ttl" {
  description = "returns a number"
  value       = data.fortios_system_ddns.this.ddns_ttl
}

output "ddns_username" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_username
}

output "ddns_zone" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ddns_zone
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.id
}

output "monitor_interface" {
  description = "returns a list of object"
  value       = data.fortios_system_ddns.this.monitor_interface
}

output "ssl_certificate" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.ssl_certificate
}

output "update_interval" {
  description = "returns a number"
  value       = data.fortios_system_ddns.this.update_interval
}

output "use_public_ip" {
  description = "returns a string"
  value       = data.fortios_system_ddns.this.use_public_ip
}

output "this" {
  value = fortios_system_ddns.this
}
```

[top](#index)