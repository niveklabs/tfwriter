# panos_panorama_gre_tunnel

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_gre_tunnel" {
  source = "./modules/panos/r/panos_panorama_gre_tunnel"

  # copy_tos - (optional) is a type of bool
  copy_tos = null
  # disabled - (optional) is a type of bool
  disabled = null
  # enable_keep_alive - (optional) is a type of bool
  enable_keep_alive = null
  # interface - (required) is a type of string
  interface = null
  # keep_alive_hold_timer - (optional) is a type of number
  keep_alive_hold_timer = null
  # keep_alive_interval - (optional) is a type of number
  keep_alive_interval = null
  # keep_alive_retry - (optional) is a type of number
  keep_alive_retry = null
  # local_address_type - (optional) is a type of string
  local_address_type = null
  # local_address_value - (required) is a type of string
  local_address_value = null
  # name - (required) is a type of string
  name = null
  # peer_address - (required) is a type of string
  peer_address = null
  # template - (required) is a type of string
  template = null
  # ttl - (optional) is a type of number
  ttl = null
  # tunnel_interface - (required) is a type of string
  tunnel_interface = null
}
```

[top](#index)

### Variables

```terraform
variable "copy_tos" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_keep_alive" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "keep_alive_hold_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keep_alive_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keep_alive_retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_address_value" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "peer_address" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel_interface" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_gre_tunnel" "this" {
  copy_tos              = var.copy_tos
  disabled              = var.disabled
  enable_keep_alive     = var.enable_keep_alive
  interface             = var.interface
  keep_alive_hold_timer = var.keep_alive_hold_timer
  keep_alive_interval   = var.keep_alive_interval
  keep_alive_retry      = var.keep_alive_retry
  local_address_type    = var.local_address_type
  local_address_value   = var.local_address_value
  name                  = var.name
  peer_address          = var.peer_address
  template              = var.template
  ttl                   = var.ttl
  tunnel_interface      = var.tunnel_interface
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_gre_tunnel.this.id
}

output "this" {
  value = panos_panorama_gre_tunnel.this
}
```

[top](#index)