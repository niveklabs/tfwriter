# aviatrix_device_transit_gateway_attachment

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_device_transit_gateway_attachment" {
  source = "./modules/aviatrix/r/aviatrix_device_transit_gateway_attachment"

  # connection_name - (required) is a type of string
  connection_name = null
  # device_bgp_asn - (required) is a type of number
  device_bgp_asn = null
  # device_name - (required) is a type of string
  device_name = null
  # enable_global_accelerator - (optional) is a type of bool
  enable_global_accelerator = null
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = null
  # local_tunnel_ip - (optional) is a type of string
  local_tunnel_ip = null
  # manual_bgp_advertised_cidrs - (optional) is a type of set of string
  manual_bgp_advertised_cidrs = []
  # phase1_authentication - (optional) is a type of string
  phase1_authentication = null
  # phase1_dh_groups - (optional) is a type of string
  phase1_dh_groups = null
  # phase1_encryption - (optional) is a type of string
  phase1_encryption = null
  # phase2_authentication - (optional) is a type of string
  phase2_authentication = null
  # phase2_dh_groups - (optional) is a type of string
  phase2_dh_groups = null
  # phase2_encryption - (optional) is a type of string
  phase2_encryption = null
  # pre_shared_key - (optional) is a type of string
  pre_shared_key = null
  # remote_tunnel_ip - (optional) is a type of string
  remote_tunnel_ip = null
  # transit_gateway_bgp_asn - (required) is a type of number
  transit_gateway_bgp_asn = null
  # transit_gateway_name - (required) is a type of string
  transit_gateway_name = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_name" {
  description = "(required) - Connection name."
  type        = string
}

variable "device_bgp_asn" {
  description = "(required) - BGP AS Number for the device."
  type        = number
}

variable "device_name" {
  description = "(required) - Device name."
  type        = string
}

variable "enable_global_accelerator" {
  description = "(optional) - Enable AWS Global Accelerator"
  type        = bool
  default     = null
}

variable "enable_learned_cidrs_approval" {
  description = "(optional) - Enable learned CIDR approval for the connection. Requires the transit_gateway's 'learned_cidrs_approval_mode' attribute be set to 'connection'. Valid values: true, false. Default value: false. Available as of provider version R2.18+."
  type        = bool
  default     = null
}

variable "local_tunnel_ip" {
  description = "(optional) - Local tunnel IP"
  type        = string
  default     = null
}

variable "manual_bgp_advertised_cidrs" {
  description = "(optional) - Configure manual BGP advertised CIDRs for this connection. Available as of provider version R2.18+."
  type        = set(string)
  default     = null
}

variable "phase1_authentication" {
  description = "(optional) - Phase 1 authentication algorithm."
  type        = string
  default     = null
}

variable "phase1_dh_groups" {
  description = "(optional) - Phase 1 Diffie-Hellman groups."
  type        = string
  default     = null
}

variable "phase1_encryption" {
  description = "(optional) - Phase 1 encryption algorithm."
  type        = string
  default     = null
}

variable "phase2_authentication" {
  description = "(optional) - Phase 2 authentication algorithm."
  type        = string
  default     = null
}

variable "phase2_dh_groups" {
  description = "(optional) - Phase 2 Diffie-Hellman groups."
  type        = string
  default     = null
}

variable "phase2_encryption" {
  description = "(optional) - Phase 2 encryption algorithm."
  type        = string
  default     = null
}

variable "pre_shared_key" {
  description = "(optional) - Pre-shared Key."
  type        = string
  default     = null
}

variable "remote_tunnel_ip" {
  description = "(optional) - Remote tunnel IP"
  type        = string
  default     = null
}

variable "transit_gateway_bgp_asn" {
  description = "(required) - BGP AS Number for transit gateway."
  type        = number
}

variable "transit_gateway_name" {
  description = "(required) - Aviatrix Transit Gateway name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_device_transit_gateway_attachment" "this" {
  # connection_name - (required) is a type of string
  connection_name = var.connection_name
  # device_bgp_asn - (required) is a type of number
  device_bgp_asn = var.device_bgp_asn
  # device_name - (required) is a type of string
  device_name = var.device_name
  # enable_global_accelerator - (optional) is a type of bool
  enable_global_accelerator = var.enable_global_accelerator
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = var.enable_learned_cidrs_approval
  # local_tunnel_ip - (optional) is a type of string
  local_tunnel_ip = var.local_tunnel_ip
  # manual_bgp_advertised_cidrs - (optional) is a type of set of string
  manual_bgp_advertised_cidrs = var.manual_bgp_advertised_cidrs
  # phase1_authentication - (optional) is a type of string
  phase1_authentication = var.phase1_authentication
  # phase1_dh_groups - (optional) is a type of string
  phase1_dh_groups = var.phase1_dh_groups
  # phase1_encryption - (optional) is a type of string
  phase1_encryption = var.phase1_encryption
  # phase2_authentication - (optional) is a type of string
  phase2_authentication = var.phase2_authentication
  # phase2_dh_groups - (optional) is a type of string
  phase2_dh_groups = var.phase2_dh_groups
  # phase2_encryption - (optional) is a type of string
  phase2_encryption = var.phase2_encryption
  # pre_shared_key - (optional) is a type of string
  pre_shared_key = var.pre_shared_key
  # remote_tunnel_ip - (optional) is a type of string
  remote_tunnel_ip = var.remote_tunnel_ip
  # transit_gateway_bgp_asn - (required) is a type of number
  transit_gateway_bgp_asn = var.transit_gateway_bgp_asn
  # transit_gateway_name - (required) is a type of string
  transit_gateway_name = var.transit_gateway_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_device_transit_gateway_attachment.this.id
}

output "this" {
  value = aviatrix_device_transit_gateway_attachment.this
}
```

[top](#index)