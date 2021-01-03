# checkpoint_physical_interface

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_physical_interface" {
  source = "./modules/checkpoint/r/checkpoint_physical_interface"

  # auto_negotiation - (optional) is a type of string
  auto_negotiation = null
  # comments - (optional) is a type of string
  comments = null
  # duplex - (optional) is a type of string
  duplex = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # ipv4_mask_length - (optional) is a type of number
  ipv4_mask_length = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # ipv6_autoconfig - (optional) is a type of string
  ipv6_autoconfig = null
  # ipv6_mask_length - (optional) is a type of number
  ipv6_mask_length = null
  # mac_addr - (optional) is a type of string
  mac_addr = null
  # monitor_mode - (optional) is a type of string
  monitor_mode = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # rx_ringsize - (optional) is a type of string
  rx_ringsize = null
  # speed - (optional) is a type of string
  speed = null
  # tx_ringsize - (optional) is a type of string
  tx_ringsize = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_negotiation" {
  description = "(optional) - Activating auto_negotiation will skip the speed and duplex configuration"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - comments"
  type        = string
  default     = null
}

variable "duplex" {
  description = "(optional) - Duplex is not relevant when 'auto_negotiation' is enabled."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipv4_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_mask_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_autoconfig" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_mask_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - interface name"
  type        = string
}

variable "rx_ringsize" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "speed" {
  description = "(optional) - Speed is not relevant when 'auto_negotiation' is enabled"
  type        = string
  default     = null
}

variable "tx_ringsize" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_physical_interface" "this" {
  auto_negotiation = var.auto_negotiation
  comments         = var.comments
  duplex           = var.duplex
  enabled          = var.enabled
  ipv4_address     = var.ipv4_address
  ipv4_mask_length = var.ipv4_mask_length
  ipv6_address     = var.ipv6_address
  ipv6_autoconfig  = var.ipv6_autoconfig
  ipv6_mask_length = var.ipv6_mask_length
  mac_addr         = var.mac_addr
  monitor_mode     = var.monitor_mode
  mtu              = var.mtu
  name             = var.name
  rx_ringsize      = var.rx_ringsize
  speed            = var.speed
  tx_ringsize      = var.tx_ringsize
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_physical_interface.this.id
}

output "this" {
  value = checkpoint_physical_interface.this
}
```

[top](#index)