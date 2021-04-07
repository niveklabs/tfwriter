# fortios_system_gretunnel

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
module "fortios_system_gretunnel" {
  source = "./modules/fortios/d/fortios_system_gretunnel"

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
data "fortios_system_gretunnel" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "checksum_reception" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.checksum_reception
}

output "checksum_transmission" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.checksum_transmission
}

output "diffservcode" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.diffservcode
}

output "dscp_copying" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.dscp_copying
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.interface
}

output "ip_version" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.ip_version
}

output "keepalive_failtimes" {
  description = "returns a number"
  value       = data.fortios_system_gretunnel.this.keepalive_failtimes
}

output "keepalive_interval" {
  description = "returns a number"
  value       = data.fortios_system_gretunnel.this.keepalive_interval
}

output "key_inbound" {
  description = "returns a number"
  value       = data.fortios_system_gretunnel.this.key_inbound
}

output "key_outbound" {
  description = "returns a number"
  value       = data.fortios_system_gretunnel.this.key_outbound
}

output "local_gw" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.local_gw
}

output "local_gw6" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.local_gw6
}

output "remote_gw" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.remote_gw
}

output "remote_gw6" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.remote_gw6
}

output "sequence_number_reception" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.sequence_number_reception
}

output "sequence_number_transmission" {
  description = "returns a string"
  value       = data.fortios_system_gretunnel.this.sequence_number_transmission
}

output "this" {
  value = fortios_system_gretunnel.this
}
```

[top](#index)