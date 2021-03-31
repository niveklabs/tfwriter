# fortios_vpnipsec_manualkeyinterface

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "fortios_vpnipsec_manualkeyinterface" {
  source = "./modules/fortios/r/fortios_vpnipsec_manualkeyinterface"

  # addr_type - (optional) is a type of string
  addr_type = null
  # auth_alg - (required) is a type of string
  auth_alg = null
  # auth_key - (optional) is a type of string
  auth_key = null
  # enc_alg - (required) is a type of string
  enc_alg = null
  # enc_key - (optional) is a type of string
  enc_key = null
  # interface - (required) is a type of string
  interface = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # local_gw - (optional) is a type of string
  local_gw = null
  # local_gw6 - (optional) is a type of string
  local_gw6 = null
  # local_spi - (optional) is a type of string
  local_spi = null
  # name - (optional) is a type of string
  name = null
  # remote_gw - (required) is a type of string
  remote_gw = null
  # remote_gw6 - (required) is a type of string
  remote_gw6 = null
  # remote_spi - (optional) is a type of string
  remote_spi = null
}
```

[top](#index)

### Variables

```terraform
variable "addr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_alg" {
  description = "(required)"
  type        = string
}

variable "auth_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enc_alg" {
  description = "(required)"
  type        = string
}

variable "enc_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_gw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_spi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_gw" {
  description = "(required)"
  type        = string
}

variable "remote_gw6" {
  description = "(required)"
  type        = string
}

variable "remote_spi" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnipsec_manualkeyinterface" "this" {
  addr_type  = var.addr_type
  auth_alg   = var.auth_alg
  auth_key   = var.auth_key
  enc_alg    = var.enc_alg
  enc_key    = var.enc_key
  interface  = var.interface
  ip_version = var.ip_version
  local_gw   = var.local_gw
  local_gw6  = var.local_gw6
  local_spi  = var.local_spi
  name       = var.name
  remote_gw  = var.remote_gw
  remote_gw6 = var.remote_gw6
  remote_spi = var.remote_spi
}
```

[top](#index)

### Outputs

```terraform
output "addr_type" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.addr_type
}

output "auth_key" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.auth_key
  sensitive   = true
}

output "enc_key" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.enc_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.id
}

output "ip_version" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.ip_version
}

output "local_gw" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.local_gw
}

output "local_gw6" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.local_gw6
}

output "local_spi" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.local_spi
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.name
}

output "remote_spi" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkeyinterface.this.remote_spi
}

output "this" {
  value = fortios_vpnipsec_manualkeyinterface.this
}
```

[top](#index)