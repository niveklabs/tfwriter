# vcd_nsxv_dnat

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_nsxv_dnat" {
  source = "./modules/vcd/r/vcd_nsxv_dnat"

  # description - (optional) is a type of string
  description = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # enabled - (optional) is a type of bool
  enabled = null
  # icmp_type - (optional) is a type of string
  icmp_type = null
  # logging_enabled - (optional) is a type of bool
  logging_enabled = null
  # network_name - (required) is a type of string
  network_name = null
  # network_type - (required) is a type of string
  network_type = null
  # org - (optional) is a type of string
  org = null
  # original_address - (required) is a type of string
  original_address = null
  # original_port - (optional) is a type of string
  original_port = null
  # protocol - (optional) is a type of string
  protocol = null
  # rule_tag - (optional) is a type of number
  rule_tag = null
  # rule_type - (optional) is a type of string
  rule_type = null
  # translated_address - (optional) is a type of string
  translated_address = null
  # translated_port - (optional) is a type of string
  translated_port = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - NAT rule description"
  type        = string
  default     = null
}

variable "edge_gateway" {
  description = "(required) - Edge gateway name in which NAT Rule is located"
  type        = string
}

variable "enabled" {
  description = "(optional) - Whether the rule should be enabled. Default 'true'"
  type        = bool
  default     = null
}

variable "icmp_type" {
  description = "(optional) - ICMP type. Only supported when protocol is ICMP. One of `any`, `address-mask-request`, `address-mask-reply`, `destination-unreachable`, `echo-request`, `echo-reply`, `parameter-problem`, `redirect`, `router-advertisement`, `router-solicitation`, `source-quench`, `time-exceeded`, `timestamp-request`, `timestamp-reply`. Default `any`"
  type        = string
  default     = null
}

variable "logging_enabled" {
  description = "(optional) - Whether logging should be enabled for this rule. Default 'false'"
  type        = bool
  default     = null
}

variable "network_name" {
  description = "(required) - Org or external network name"
  type        = string
}

variable "network_type" {
  description = "(required) - Network type. One of 'ext', 'org'"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "original_address" {
  description = "(required) - Original address or address range. This is the the destination address for DNAT rules."
  type        = string
}

variable "original_port" {
  description = "(optional) - Original port. This is the destination port for DNAT rules"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - Protocol. Such as 'tcp', 'udp', 'icmp', 'any'"
  type        = string
  default     = null
}

variable "rule_tag" {
  description = "(optional) - Optional. Allows to set custom rule tag"
  type        = number
  default     = null
}

variable "rule_type" {
  description = "(optional) - Read only. Possible values 'user', 'internal_high'"
  type        = string
  default     = null
}

variable "translated_address" {
  description = "(optional) - Translated address or address range"
  type        = string
  default     = null
}

variable "translated_port" {
  description = "(optional) - Translated port"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_nsxv_dnat" "this" {
  # description - (optional) is a type of string
  description = var.description
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # icmp_type - (optional) is a type of string
  icmp_type = var.icmp_type
  # logging_enabled - (optional) is a type of bool
  logging_enabled = var.logging_enabled
  # network_name - (required) is a type of string
  network_name = var.network_name
  # network_type - (required) is a type of string
  network_type = var.network_type
  # org - (optional) is a type of string
  org = var.org
  # original_address - (required) is a type of string
  original_address = var.original_address
  # original_port - (optional) is a type of string
  original_port = var.original_port
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # rule_tag - (optional) is a type of number
  rule_tag = var.rule_tag
  # rule_type - (optional) is a type of string
  rule_type = var.rule_type
  # translated_address - (optional) is a type of string
  translated_address = var.translated_address
  # translated_port - (optional) is a type of string
  translated_port = var.translated_port
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_nsxv_dnat.this.id
}

output "rule_tag" {
  description = "returns a number"
  value       = vcd_nsxv_dnat.this.rule_tag
}

output "rule_type" {
  description = "returns a string"
  value       = vcd_nsxv_dnat.this.rule_type
}

output "this" {
  value = vcd_nsxv_dnat.this
}
```

[top](#index)