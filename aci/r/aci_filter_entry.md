# aci_filter_entry

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_filter_entry" {
  source = "./modules/aci/r/aci_filter_entry"

  # annotation - (optional) is a type of string
  annotation = null
  # apply_to_frag - (optional) is a type of string
  apply_to_frag = null
  # arp_opc - (optional) is a type of string
  arp_opc = null
  # d_from_port - (optional) is a type of string
  d_from_port = null
  # d_to_port - (optional) is a type of string
  d_to_port = null
  # description - (optional) is a type of string
  description = null
  # ether_t - (optional) is a type of string
  ether_t = null
  # filter_dn - (required) is a type of string
  filter_dn = null
  # icmpv4_t - (optional) is a type of string
  icmpv4_t = null
  # icmpv6_t - (optional) is a type of string
  icmpv6_t = null
  # match_dscp - (optional) is a type of string
  match_dscp = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # prot - (optional) is a type of string
  prot = null
  # s_from_port - (optional) is a type of string
  s_from_port = null
  # s_to_port - (optional) is a type of string
  s_to_port = null
  # stateful - (optional) is a type of string
  stateful = null
  # tcp_rules - (optional) is a type of string
  tcp_rules = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "apply_to_frag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_opc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "d_from_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "d_to_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ether_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_dn" {
  description = "(required)"
  type        = string
}

variable "icmpv4_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmpv6_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prot" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s_from_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s_to_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stateful" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_rules" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_filter_entry" "this" {
  annotation    = var.annotation
  apply_to_frag = var.apply_to_frag
  arp_opc       = var.arp_opc
  d_from_port   = var.d_from_port
  d_to_port     = var.d_to_port
  description   = var.description
  ether_t       = var.ether_t
  filter_dn     = var.filter_dn
  icmpv4_t      = var.icmpv4_t
  icmpv6_t      = var.icmpv6_t
  match_dscp    = var.match_dscp
  name          = var.name
  name_alias    = var.name_alias
  prot          = var.prot
  s_from_port   = var.s_from_port
  s_to_port     = var.s_to_port
  stateful      = var.stateful
  tcp_rules     = var.tcp_rules
}
```

[top](#index)

### Outputs

```terraform
output "apply_to_frag" {
  description = "returns a string"
  value       = aci_filter_entry.this.apply_to_frag
}

output "arp_opc" {
  description = "returns a string"
  value       = aci_filter_entry.this.arp_opc
}

output "d_from_port" {
  description = "returns a string"
  value       = aci_filter_entry.this.d_from_port
}

output "d_to_port" {
  description = "returns a string"
  value       = aci_filter_entry.this.d_to_port
}

output "description" {
  description = "returns a string"
  value       = aci_filter_entry.this.description
}

output "ether_t" {
  description = "returns a string"
  value       = aci_filter_entry.this.ether_t
}

output "icmpv4_t" {
  description = "returns a string"
  value       = aci_filter_entry.this.icmpv4_t
}

output "icmpv6_t" {
  description = "returns a string"
  value       = aci_filter_entry.this.icmpv6_t
}

output "id" {
  description = "returns a string"
  value       = aci_filter_entry.this.id
}

output "match_dscp" {
  description = "returns a string"
  value       = aci_filter_entry.this.match_dscp
}

output "name_alias" {
  description = "returns a string"
  value       = aci_filter_entry.this.name_alias
}

output "prot" {
  description = "returns a string"
  value       = aci_filter_entry.this.prot
}

output "s_from_port" {
  description = "returns a string"
  value       = aci_filter_entry.this.s_from_port
}

output "s_to_port" {
  description = "returns a string"
  value       = aci_filter_entry.this.s_to_port
}

output "stateful" {
  description = "returns a string"
  value       = aci_filter_entry.this.stateful
}

output "tcp_rules" {
  description = "returns a string"
  value       = aci_filter_entry.this.tcp_rules
}

output "this" {
  value = aci_filter_entry.this
}
```

[top](#index)