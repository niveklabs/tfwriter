# fortios_system_fortisandbox

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
module "fortios_system_fortisandbox" {
  source = "./modules/fortios/d/fortios_system_fortisandbox"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_fortisandbox" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.email
}

output "enc_algorithm" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.enc_algorithm
}

output "forticloud" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.forticloud
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.interface_select_method
}

output "server" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_fortisandbox.this.status
}

output "this" {
  value = fortios_system_fortisandbox.this
}
```

[top](#index)