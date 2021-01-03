# fortios_vpn_ipsec_phase2interface

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_vpn_ipsec_phase2interface" {
  source = "./modules/fortios/r/fortios_vpn_ipsec_phase2interface"

  # comments - (optional) is a type of string
  comments = null
  # dst_addr_type - (optional) is a type of string
  dst_addr_type = null
  # dst_end_ip - (optional) is a type of string
  dst_end_ip = null
  # dst_name - (optional) is a type of string
  dst_name = null
  # dst_start_ip - (optional) is a type of string
  dst_start_ip = null
  # dst_subnet - (optional) is a type of string
  dst_subnet = null
  # name - (required) is a type of string
  name = null
  # phase1name - (required) is a type of string
  phase1name = null
  # proposal - (optional) is a type of string
  proposal = null
  # src_addr_type - (optional) is a type of string
  src_addr_type = null
  # src_end_ip - (optional) is a type of string
  src_end_ip = null
  # src_name - (optional) is a type of string
  src_name = null
  # src_start_ip - (optional) is a type of string
  src_start_ip = null
  # src_subnet - (optional) is a type of string
  src_subnet = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_addr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "phase1name" {
  description = "(required)"
  type        = string
}

variable "proposal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_addr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_subnet" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpn_ipsec_phase2interface" "this" {
  comments      = var.comments
  dst_addr_type = var.dst_addr_type
  dst_end_ip    = var.dst_end_ip
  dst_name      = var.dst_name
  dst_start_ip  = var.dst_start_ip
  dst_subnet    = var.dst_subnet
  name          = var.name
  phase1name    = var.phase1name
  proposal      = var.proposal
  src_addr_type = var.src_addr_type
  src_end_ip    = var.src_end_ip
  src_name      = var.src_name
  src_start_ip  = var.src_start_ip
  src_subnet    = var.src_subnet
}
```

[top](#index)

### Outputs

```terraform
output "dst_addr_type" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.dst_addr_type
}

output "dst_end_ip" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.dst_end_ip
}

output "dst_name" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.dst_name
}

output "dst_start_ip" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.dst_start_ip
}

output "dst_subnet" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.dst_subnet
}

output "id" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.id
}

output "proposal" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.proposal
}

output "src_addr_type" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.src_addr_type
}

output "src_end_ip" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.src_end_ip
}

output "src_name" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.src_name
}

output "src_start_ip" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.src_start_ip
}

output "src_subnet" {
  description = "returns a string"
  value       = fortios_vpn_ipsec_phase2interface.this.src_subnet
}

output "this" {
  value = fortios_vpn_ipsec_phase2interface.this
}
```

[top](#index)