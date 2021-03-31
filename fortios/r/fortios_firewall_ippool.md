# fortios_firewall_ippool

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
module "fortios_firewall_ippool" {
  source = "./modules/fortios/r/fortios_firewall_ippool"

  # arp_intf - (optional) is a type of string
  arp_intf = null
  # arp_reply - (optional) is a type of string
  arp_reply = null
  # associated_interface - (optional) is a type of string
  associated_interface = null
  # block_size - (optional) is a type of number
  block_size = null
  # comments - (optional) is a type of string
  comments = null
  # endip - (required) is a type of string
  endip = null
  # endport - (optional) is a type of number
  endport = null
  # name - (optional) is a type of string
  name = null
  # num_blocks_per_user - (optional) is a type of number
  num_blocks_per_user = null
  # pba_timeout - (optional) is a type of number
  pba_timeout = null
  # permit_any_host - (optional) is a type of string
  permit_any_host = null
  # port_per_user - (optional) is a type of number
  port_per_user = null
  # source_endip - (optional) is a type of string
  source_endip = null
  # source_startip - (optional) is a type of string
  source_startip = null
  # startip - (required) is a type of string
  startip = null
  # startport - (optional) is a type of number
  startport = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "arp_intf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_reply" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "associated_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endip" {
  description = "(required)"
  type        = string
}

variable "endport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_blocks_per_user" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pba_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "permit_any_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_per_user" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_endip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_startip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "startip" {
  description = "(required)"
  type        = string
}

variable "startport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_ippool" "this" {
  arp_intf             = var.arp_intf
  arp_reply            = var.arp_reply
  associated_interface = var.associated_interface
  block_size           = var.block_size
  comments             = var.comments
  endip                = var.endip
  endport              = var.endport
  name                 = var.name
  num_blocks_per_user  = var.num_blocks_per_user
  pba_timeout          = var.pba_timeout
  permit_any_host      = var.permit_any_host
  port_per_user        = var.port_per_user
  source_endip         = var.source_endip
  source_startip       = var.source_startip
  startip              = var.startip
  startport            = var.startport
  type                 = var.type
}
```

[top](#index)

### Outputs

```terraform
output "arp_intf" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.arp_intf
}

output "arp_reply" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.arp_reply
}

output "associated_interface" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.associated_interface
}

output "block_size" {
  description = "returns a number"
  value       = fortios_firewall_ippool.this.block_size
}

output "endport" {
  description = "returns a number"
  value       = fortios_firewall_ippool.this.endport
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.name
}

output "num_blocks_per_user" {
  description = "returns a number"
  value       = fortios_firewall_ippool.this.num_blocks_per_user
}

output "pba_timeout" {
  description = "returns a number"
  value       = fortios_firewall_ippool.this.pba_timeout
}

output "permit_any_host" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.permit_any_host
}

output "port_per_user" {
  description = "returns a number"
  value       = fortios_firewall_ippool.this.port_per_user
}

output "source_endip" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.source_endip
}

output "source_startip" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.source_startip
}

output "startport" {
  description = "returns a number"
  value       = fortios_firewall_ippool.this.startport
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_ippool.this.type
}

output "this" {
  value = fortios_firewall_ippool.this
}
```

[top](#index)