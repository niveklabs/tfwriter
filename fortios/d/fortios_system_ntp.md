# fortios_system_ntp

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
module "fortios_system_ntp" {
  source = "./modules/fortios/d/fortios_system_ntp"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_ntp" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "authentication" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.authentication
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = data.fortios_system_ntp.this.interface
}

output "key" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.key
  sensitive   = true
}

output "key_id" {
  description = "returns a number"
  value       = data.fortios_system_ntp.this.key_id
}

output "key_type" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.key_type
}

output "ntpserver" {
  description = "returns a list of object"
  value       = data.fortios_system_ntp.this.ntpserver
}

output "ntpsync" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.ntpsync
}

output "server_mode" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.server_mode
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.source_ip6
}

output "syncinterval" {
  description = "returns a number"
  value       = data.fortios_system_ntp.this.syncinterval
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_ntp.this.type
}

output "this" {
  value = fortios_system_ntp.this
}
```

[top](#index)