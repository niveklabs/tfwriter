# panos_anti_spyware_security_profile

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
module "panos_anti_spyware_security_profile" {
  source = "./modules/panos/d/panos_anti_spyware_security_profile"

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
data "panos_anti_spyware_security_profile" "this" {
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "botnet_list" {
  description = "returns a list of object"
  value       = data.panos_anti_spyware_security_profile.this.botnet_list
}

output "description" {
  description = "returns a string"
  value       = data.panos_anti_spyware_security_profile.this.description
}

output "dns_category" {
  description = "returns a list of object"
  value       = data.panos_anti_spyware_security_profile.this.dns_category
}

output "exception" {
  description = "returns a list of object"
  value       = data.panos_anti_spyware_security_profile.this.exception
}

output "id" {
  description = "returns a string"
  value       = data.panos_anti_spyware_security_profile.this.id
}

output "packet_capture" {
  description = "returns a string"
  value       = data.panos_anti_spyware_security_profile.this.packet_capture
}

output "rule" {
  description = "returns a list of object"
  value       = data.panos_anti_spyware_security_profile.this.rule
}

output "sinkhole_ipv4_address" {
  description = "returns a string"
  value       = data.panos_anti_spyware_security_profile.this.sinkhole_ipv4_address
}

output "sinkhole_ipv6_address" {
  description = "returns a string"
  value       = data.panos_anti_spyware_security_profile.this.sinkhole_ipv6_address
}

output "threat_exceptions" {
  description = "returns a list of string"
  value       = data.panos_anti_spyware_security_profile.this.threat_exceptions
}

output "white_list" {
  description = "returns a list of object"
  value       = data.panos_anti_spyware_security_profile.this.white_list
}

output "this" {
  value = panos_anti_spyware_security_profile.this
}
```

[top](#index)