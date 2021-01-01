# aws_vpn_connection

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_vpn_connection" {
  source = "./modules/aws/r/aws_vpn_connection"

  # customer_gateway_id - (required) is a type of string
  customer_gateway_id = null
  # enable_acceleration - (optional) is a type of bool
  enable_acceleration = null
  # local_ipv4_network_cidr - (optional) is a type of string
  local_ipv4_network_cidr = null
  # local_ipv6_network_cidr - (optional) is a type of string
  local_ipv6_network_cidr = null
  # remote_ipv4_network_cidr - (optional) is a type of string
  remote_ipv4_network_cidr = null
  # remote_ipv6_network_cidr - (optional) is a type of string
  remote_ipv6_network_cidr = null
  # static_routes_only - (optional) is a type of bool
  static_routes_only = null
  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_id - (optional) is a type of string
  transit_gateway_id = null
  # tunnel1_dpd_timeout_action - (optional) is a type of string
  tunnel1_dpd_timeout_action = null
  # tunnel1_dpd_timeout_seconds - (optional) is a type of number
  tunnel1_dpd_timeout_seconds = null
  # tunnel1_ike_versions - (optional) is a type of set of string
  tunnel1_ike_versions = []
  # tunnel1_inside_cidr - (optional) is a type of string
  tunnel1_inside_cidr = null
  # tunnel1_inside_ipv6_cidr - (optional) is a type of string
  tunnel1_inside_ipv6_cidr = null
  # tunnel1_phase1_dh_group_numbers - (optional) is a type of set of number
  tunnel1_phase1_dh_group_numbers = []
  # tunnel1_phase1_encryption_algorithms - (optional) is a type of set of string
  tunnel1_phase1_encryption_algorithms = []
  # tunnel1_phase1_integrity_algorithms - (optional) is a type of set of string
  tunnel1_phase1_integrity_algorithms = []
  # tunnel1_phase1_lifetime_seconds - (optional) is a type of number
  tunnel1_phase1_lifetime_seconds = null
  # tunnel1_phase2_dh_group_numbers - (optional) is a type of set of number
  tunnel1_phase2_dh_group_numbers = []
  # tunnel1_phase2_encryption_algorithms - (optional) is a type of set of string
  tunnel1_phase2_encryption_algorithms = []
  # tunnel1_phase2_integrity_algorithms - (optional) is a type of set of string
  tunnel1_phase2_integrity_algorithms = []
  # tunnel1_phase2_lifetime_seconds - (optional) is a type of number
  tunnel1_phase2_lifetime_seconds = null
  # tunnel1_preshared_key - (optional) is a type of string
  tunnel1_preshared_key = null
  # tunnel1_rekey_fuzz_percentage - (optional) is a type of number
  tunnel1_rekey_fuzz_percentage = null
  # tunnel1_rekey_margin_time_seconds - (optional) is a type of number
  tunnel1_rekey_margin_time_seconds = null
  # tunnel1_replay_window_size - (optional) is a type of number
  tunnel1_replay_window_size = null
  # tunnel1_startup_action - (optional) is a type of string
  tunnel1_startup_action = null
  # tunnel2_dpd_timeout_action - (optional) is a type of string
  tunnel2_dpd_timeout_action = null
  # tunnel2_dpd_timeout_seconds - (optional) is a type of number
  tunnel2_dpd_timeout_seconds = null
  # tunnel2_ike_versions - (optional) is a type of set of string
  tunnel2_ike_versions = []
  # tunnel2_inside_cidr - (optional) is a type of string
  tunnel2_inside_cidr = null
  # tunnel2_inside_ipv6_cidr - (optional) is a type of string
  tunnel2_inside_ipv6_cidr = null
  # tunnel2_phase1_dh_group_numbers - (optional) is a type of set of number
  tunnel2_phase1_dh_group_numbers = []
  # tunnel2_phase1_encryption_algorithms - (optional) is a type of set of string
  tunnel2_phase1_encryption_algorithms = []
  # tunnel2_phase1_integrity_algorithms - (optional) is a type of set of string
  tunnel2_phase1_integrity_algorithms = []
  # tunnel2_phase1_lifetime_seconds - (optional) is a type of number
  tunnel2_phase1_lifetime_seconds = null
  # tunnel2_phase2_dh_group_numbers - (optional) is a type of set of number
  tunnel2_phase2_dh_group_numbers = []
  # tunnel2_phase2_encryption_algorithms - (optional) is a type of set of string
  tunnel2_phase2_encryption_algorithms = []
  # tunnel2_phase2_integrity_algorithms - (optional) is a type of set of string
  tunnel2_phase2_integrity_algorithms = []
  # tunnel2_phase2_lifetime_seconds - (optional) is a type of number
  tunnel2_phase2_lifetime_seconds = null
  # tunnel2_preshared_key - (optional) is a type of string
  tunnel2_preshared_key = null
  # tunnel2_rekey_fuzz_percentage - (optional) is a type of number
  tunnel2_rekey_fuzz_percentage = null
  # tunnel2_rekey_margin_time_seconds - (optional) is a type of number
  tunnel2_rekey_margin_time_seconds = null
  # tunnel2_replay_window_size - (optional) is a type of number
  tunnel2_replay_window_size = null
  # tunnel2_startup_action - (optional) is a type of string
  tunnel2_startup_action = null
  # tunnel_inside_ip_version - (optional) is a type of string
  tunnel_inside_ip_version = null
  # type - (required) is a type of string
  type = null
  # vpn_gateway_id - (optional) is a type of string
  vpn_gateway_id = null
}
```

[top](#index)

### Variables

```hcl
variable "customer_gateway_id" {
  description = "(required)"
  type        = string
}

variable "enable_acceleration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "local_ipv4_network_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_ipv6_network_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_ipv4_network_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_ipv6_network_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "static_routes_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transit_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel1_dpd_timeout_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel1_dpd_timeout_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel1_ike_versions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel1_inside_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel1_inside_ipv6_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel1_phase1_dh_group_numbers" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "tunnel1_phase1_encryption_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel1_phase1_integrity_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel1_phase1_lifetime_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel1_phase2_dh_group_numbers" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "tunnel1_phase2_encryption_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel1_phase2_integrity_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel1_phase2_lifetime_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel1_preshared_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel1_rekey_fuzz_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel1_rekey_margin_time_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel1_replay_window_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel1_startup_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel2_dpd_timeout_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel2_dpd_timeout_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel2_ike_versions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel2_inside_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel2_inside_ipv6_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel2_phase1_dh_group_numbers" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "tunnel2_phase1_encryption_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel2_phase1_integrity_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel2_phase1_lifetime_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel2_phase2_dh_group_numbers" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "tunnel2_phase2_encryption_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel2_phase2_integrity_algorithms" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tunnel2_phase2_lifetime_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel2_preshared_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel2_rekey_fuzz_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel2_rekey_margin_time_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel2_replay_window_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel2_startup_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_inside_ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "vpn_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_vpn_connection" "this" {
  customer_gateway_id                  = var.customer_gateway_id
  enable_acceleration                  = var.enable_acceleration
  local_ipv4_network_cidr              = var.local_ipv4_network_cidr
  local_ipv6_network_cidr              = var.local_ipv6_network_cidr
  remote_ipv4_network_cidr             = var.remote_ipv4_network_cidr
  remote_ipv6_network_cidr             = var.remote_ipv6_network_cidr
  static_routes_only                   = var.static_routes_only
  tags                                 = var.tags
  transit_gateway_id                   = var.transit_gateway_id
  tunnel1_dpd_timeout_action           = var.tunnel1_dpd_timeout_action
  tunnel1_dpd_timeout_seconds          = var.tunnel1_dpd_timeout_seconds
  tunnel1_ike_versions                 = var.tunnel1_ike_versions
  tunnel1_inside_cidr                  = var.tunnel1_inside_cidr
  tunnel1_inside_ipv6_cidr             = var.tunnel1_inside_ipv6_cidr
  tunnel1_phase1_dh_group_numbers      = var.tunnel1_phase1_dh_group_numbers
  tunnel1_phase1_encryption_algorithms = var.tunnel1_phase1_encryption_algorithms
  tunnel1_phase1_integrity_algorithms  = var.tunnel1_phase1_integrity_algorithms
  tunnel1_phase1_lifetime_seconds      = var.tunnel1_phase1_lifetime_seconds
  tunnel1_phase2_dh_group_numbers      = var.tunnel1_phase2_dh_group_numbers
  tunnel1_phase2_encryption_algorithms = var.tunnel1_phase2_encryption_algorithms
  tunnel1_phase2_integrity_algorithms  = var.tunnel1_phase2_integrity_algorithms
  tunnel1_phase2_lifetime_seconds      = var.tunnel1_phase2_lifetime_seconds
  tunnel1_preshared_key                = var.tunnel1_preshared_key
  tunnel1_rekey_fuzz_percentage        = var.tunnel1_rekey_fuzz_percentage
  tunnel1_rekey_margin_time_seconds    = var.tunnel1_rekey_margin_time_seconds
  tunnel1_replay_window_size           = var.tunnel1_replay_window_size
  tunnel1_startup_action               = var.tunnel1_startup_action
  tunnel2_dpd_timeout_action           = var.tunnel2_dpd_timeout_action
  tunnel2_dpd_timeout_seconds          = var.tunnel2_dpd_timeout_seconds
  tunnel2_ike_versions                 = var.tunnel2_ike_versions
  tunnel2_inside_cidr                  = var.tunnel2_inside_cidr
  tunnel2_inside_ipv6_cidr             = var.tunnel2_inside_ipv6_cidr
  tunnel2_phase1_dh_group_numbers      = var.tunnel2_phase1_dh_group_numbers
  tunnel2_phase1_encryption_algorithms = var.tunnel2_phase1_encryption_algorithms
  tunnel2_phase1_integrity_algorithms  = var.tunnel2_phase1_integrity_algorithms
  tunnel2_phase1_lifetime_seconds      = var.tunnel2_phase1_lifetime_seconds
  tunnel2_phase2_dh_group_numbers      = var.tunnel2_phase2_dh_group_numbers
  tunnel2_phase2_encryption_algorithms = var.tunnel2_phase2_encryption_algorithms
  tunnel2_phase2_integrity_algorithms  = var.tunnel2_phase2_integrity_algorithms
  tunnel2_phase2_lifetime_seconds      = var.tunnel2_phase2_lifetime_seconds
  tunnel2_preshared_key                = var.tunnel2_preshared_key
  tunnel2_rekey_fuzz_percentage        = var.tunnel2_rekey_fuzz_percentage
  tunnel2_rekey_margin_time_seconds    = var.tunnel2_rekey_margin_time_seconds
  tunnel2_replay_window_size           = var.tunnel2_replay_window_size
  tunnel2_startup_action               = var.tunnel2_startup_action
  tunnel_inside_ip_version             = var.tunnel_inside_ip_version
  type                                 = var.type
  vpn_gateway_id                       = var.vpn_gateway_id
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_vpn_connection.this.arn
}

output "customer_gateway_configuration" {
  description = "returns a string"
  value       = aws_vpn_connection.this.customer_gateway_configuration
}

output "enable_acceleration" {
  description = "returns a bool"
  value       = aws_vpn_connection.this.enable_acceleration
}

output "id" {
  description = "returns a string"
  value       = aws_vpn_connection.this.id
}

output "local_ipv4_network_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.local_ipv4_network_cidr
}

output "local_ipv6_network_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.local_ipv6_network_cidr
}

output "remote_ipv4_network_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.remote_ipv4_network_cidr
}

output "remote_ipv6_network_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.remote_ipv6_network_cidr
}

output "routes" {
  description = "returns a set of object"
  value       = aws_vpn_connection.this.routes
}

output "static_routes_only" {
  description = "returns a bool"
  value       = aws_vpn_connection.this.static_routes_only
}

output "transit_gateway_attachment_id" {
  description = "returns a string"
  value       = aws_vpn_connection.this.transit_gateway_attachment_id
}

output "tunnel1_address" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_address
}

output "tunnel1_bgp_asn" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_bgp_asn
}

output "tunnel1_bgp_holdtime" {
  description = "returns a number"
  value       = aws_vpn_connection.this.tunnel1_bgp_holdtime
}

output "tunnel1_cgw_inside_address" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_cgw_inside_address
}

output "tunnel1_inside_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_inside_cidr
}

output "tunnel1_inside_ipv6_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_inside_ipv6_cidr
}

output "tunnel1_preshared_key" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_preshared_key
  sensitive   = true
}

output "tunnel1_vgw_inside_address" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel1_vgw_inside_address
}

output "tunnel2_address" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_address
}

output "tunnel2_bgp_asn" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_bgp_asn
}

output "tunnel2_bgp_holdtime" {
  description = "returns a number"
  value       = aws_vpn_connection.this.tunnel2_bgp_holdtime
}

output "tunnel2_cgw_inside_address" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_cgw_inside_address
}

output "tunnel2_inside_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_inside_cidr
}

output "tunnel2_inside_ipv6_cidr" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_inside_ipv6_cidr
}

output "tunnel2_preshared_key" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_preshared_key
  sensitive   = true
}

output "tunnel2_vgw_inside_address" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel2_vgw_inside_address
}

output "tunnel_inside_ip_version" {
  description = "returns a string"
  value       = aws_vpn_connection.this.tunnel_inside_ip_version
}

output "vgw_telemetry" {
  description = "returns a set of object"
  value       = aws_vpn_connection.this.vgw_telemetry
}

output "this" {
  value = aws_vpn_connection.this
}
```

[top](#index)