# fortios_vpn_ipsec_phase1interface

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
module "fortios_vpn_ipsec_phase1interface" {
  source = "./modules/fortios/r/fortios_vpn_ipsec_phase1interface"

  # authmethod - (optional) is a type of string
  authmethod = null
  # authmethod_remote - (optional) is a type of string
  authmethod_remote = null
  # certificate - (optional) is a type of list of string
  certificate = []
  # comments - (optional) is a type of string
  comments = null
  # interface - (required) is a type of string
  interface = null
  # ipv4_split_exclude - (optional) is a type of string
  ipv4_split_exclude = null
  # ipv4_split_include - (optional) is a type of string
  ipv4_split_include = null
  # mode_cfg - (optional) is a type of string
  mode_cfg = null
  # name - (required) is a type of string
  name = null
  # peer - (optional) is a type of string
  peer = null
  # peergrp - (optional) is a type of string
  peergrp = null
  # peerid - (optional) is a type of string
  peerid = null
  # peertype - (optional) is a type of string
  peertype = null
  # proposal - (optional) is a type of string
  proposal = null
  # psksecret - (required) is a type of string
  psksecret = null
  # remote_gw - (required) is a type of string
  remote_gw = null
  # split_include_service - (optional) is a type of string
  split_include_service = null
  # type - (required) is a type of string
  type = null
  # wizard_type - (optional) is a type of string
  wizard_type = null
}
```

[top](#index)

### Variables

```terraform
variable "authmethod" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authmethod_remote" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ipv4_split_exclude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_split_include" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode_cfg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "peer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peergrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peerid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peertype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proposal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "psksecret" {
  description = "(required)"
  type        = string
}

variable "remote_gw" {
  description = "(required)"
  type        = string
}

variable "split_include_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "wizard_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpn_ipsec_phase1interface" "this" {
  # authmethod - (optional) is a type of string
  authmethod = var.authmethod
  # authmethod_remote - (optional) is a type of string
  authmethod_remote = var.authmethod_remote
  # certificate - (optional) is a type of list of string
  certificate = var.certificate
  # comments - (optional) is a type of string
  comments = var.comments
  # interface - (required) is a type of string
  interface = var.interface
  # ipv4_split_exclude - (optional) is a type of string
  ipv4_split_exclude = var.ipv4_split_exclude
  # ipv4_split_include - (optional) is a type of string
  ipv4_split_include = var.ipv4_split_include
  # mode_cfg - (optional) is a type of string
  mode_cfg = var.mode_cfg
  # name - (required) is a type of string
  name = var.name
  # peer - (optional) is a type of string
  peer = var.peer
  # peergrp - (optional) is a type of string
  peergrp = var.peergrp
  # peerid - (optional) is a type of string
  peerid = var.peerid
  # peertype - (optional) is a type of string
  peertype = var.peertype
  # proposal - (optional) is a type of string
  proposal = var.proposal
  # psksecret - (required) is a type of string
  psksecret = var.psksecret
  # remote_gw - (required) is a type of string
  remote_gw = var.remote_gw
  # split_include_service - (optional) is a type of string
  split_include_service = var.split_include_service
  # type - (required) is a type of string
  type = var.type
  # wizard_type - (optional) is a type of string
  wizard_type = var.wizard_type
}
```

[top](#index)

### Outputs

```terraform
output "authmethod" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.authmethod
}

output "authmethod_remote" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.authmethod_remote
}

output "certificate" {
  description = "returns a list of string"
  value       = fortios_vpn_ipsec_phase1interface.this.certificate
}

output "id" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.id
}

output "ipv4_split_exclude" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.ipv4_split_exclude
}

output "ipv4_split_include" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.ipv4_split_include
}

output "mode_cfg" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.mode_cfg
}

output "peer" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.peer
}

output "peergrp" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.peergrp
}

output "peerid" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.peerid
}

output "peertype" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.peertype
}

output "proposal" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.proposal
}

output "split_include_service" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.split_include_service
}

output "wizard_type" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase1interface.this.wizard_type
}

output "this" {
  value = fortios_vpn_ipsec_phase1interface.this
}
```

[top](#index)