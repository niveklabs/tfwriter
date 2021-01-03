# panos_panorama_ipsec_tunnel_proxy_id_ipv4

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
module "panos_panorama_ipsec_tunnel_proxy_id_ipv4" {
  source = "./modules/panos/r/panos_panorama_ipsec_tunnel_proxy_id_ipv4"

  # ipsec_tunnel - (required) is a type of string
  ipsec_tunnel = null
  # local - (optional) is a type of string
  local = null
  # name - (required) is a type of string
  name = null
  # protocol_any - (optional) is a type of bool
  protocol_any = null
  # protocol_number - (optional) is a type of number
  protocol_number = null
  # protocol_tcp_local - (optional) is a type of number
  protocol_tcp_local = null
  # protocol_tcp_remote - (optional) is a type of number
  protocol_tcp_remote = null
  # protocol_udp_local - (optional) is a type of number
  protocol_udp_local = null
  # protocol_udp_remote - (optional) is a type of number
  protocol_udp_remote = null
  # remote - (optional) is a type of string
  remote = null
  # template - (required) is a type of string
  template = null
}
```

[top](#index)

### Variables

```terraform
variable "ipsec_tunnel" {
  description = "(required)"
  type        = string
}

variable "local" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol_any" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "protocol_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol_tcp_local" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol_tcp_remote" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol_udp_local" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol_udp_remote" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remote" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_ipsec_tunnel_proxy_id_ipv4" "this" {
  ipsec_tunnel        = var.ipsec_tunnel
  local               = var.local
  name                = var.name
  protocol_any        = var.protocol_any
  protocol_number     = var.protocol_number
  protocol_tcp_local  = var.protocol_tcp_local
  protocol_tcp_remote = var.protocol_tcp_remote
  protocol_udp_local  = var.protocol_udp_local
  protocol_udp_remote = var.protocol_udp_remote
  remote              = var.remote
  template            = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_ipsec_tunnel_proxy_id_ipv4.this.id
}

output "this" {
  value = panos_panorama_ipsec_tunnel_proxy_id_ipv4.this
}
```

[top](#index)