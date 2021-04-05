# panos_dos_protection_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_dos_protection_profile" {
  source = "./modules/panos/d/panos_dos_protection_profile"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_dos_protection_profile" "this" {
  device_group = var.device_group
  name         = var.name
  vsys         = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.panos_dos_protection_profile.this.description
}

output "enable_sessions_protections" {
  description = "returns a bool"
  value       = data.panos_dos_protection_profile.this.enable_sessions_protections
}

output "icmp" {
  description = "returns a list of object"
  value       = data.panos_dos_protection_profile.this.icmp
}

output "icmpv6" {
  description = "returns a list of object"
  value       = data.panos_dos_protection_profile.this.icmpv6
}

output "id" {
  description = "returns a string"
  value       = data.panos_dos_protection_profile.this.id
}

output "max_concurrent_sessions" {
  description = "returns a number"
  value       = data.panos_dos_protection_profile.this.max_concurrent_sessions
}

output "other" {
  description = "returns a list of object"
  value       = data.panos_dos_protection_profile.this.other
}

output "syn" {
  description = "returns a list of object"
  value       = data.panos_dos_protection_profile.this.syn
}

output "type" {
  description = "returns a string"
  value       = data.panos_dos_protection_profile.this.type
}

output "udp" {
  description = "returns a list of object"
  value       = data.panos_dos_protection_profile.this.udp
}

output "this" {
  value = panos_dos_protection_profile.this
}
```

[top](#index)