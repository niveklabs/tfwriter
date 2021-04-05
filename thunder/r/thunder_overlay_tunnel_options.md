# thunder_overlay_tunnel_options

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_overlay_tunnel_options" {
  source = "./modules/thunder/r/thunder_overlay_tunnel_options"

  # gateway_mac - (optional) is a type of string
  gateway_mac = null
  # ip_dscp_preserve - (optional) is a type of number
  ip_dscp_preserve = null
  # nvgre_disable_flow_id - (optional) is a type of number
  nvgre_disable_flow_id = null
  # nvgre_key_mode_lower24 - (optional) is a type of number
  nvgre_key_mode_lower24 = null
  # tcp_mss_adjust_disable - (optional) is a type of number
  tcp_mss_adjust_disable = null
  # uuid - (optional) is a type of string
  uuid = null
  # vxlan_dest_port - (optional) is a type of number
  vxlan_dest_port = null
}
```

[top](#index)

### Variables

```terraform
variable "gateway_mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_dscp_preserve" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nvgre_disable_flow_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nvgre_key_mode_lower24" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_mss_adjust_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vxlan_dest_port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_overlay_tunnel_options" "this" {
  gateway_mac            = var.gateway_mac
  ip_dscp_preserve       = var.ip_dscp_preserve
  nvgre_disable_flow_id  = var.nvgre_disable_flow_id
  nvgre_key_mode_lower24 = var.nvgre_key_mode_lower24
  tcp_mss_adjust_disable = var.tcp_mss_adjust_disable
  uuid                   = var.uuid
  vxlan_dest_port        = var.vxlan_dest_port
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_overlay_tunnel_options.this.id
}

output "this" {
  value = thunder_overlay_tunnel_options.this
}
```

[top](#index)