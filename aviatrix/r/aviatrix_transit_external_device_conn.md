# aviatrix_transit_external_device_conn

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
module "aviatrix_transit_external_device_conn" {
  source = "./modules/aviatrix/r/aviatrix_transit_external_device_conn"

  # backup_bgp_remote_as_num - (optional) is a type of string
  backup_bgp_remote_as_num = null
  # backup_direct_connect - (optional) is a type of bool
  backup_direct_connect = null
  # backup_local_lan_ip - (optional) is a type of string
  backup_local_lan_ip = null
  # backup_local_tunnel_cidr - (optional) is a type of string
  backup_local_tunnel_cidr = null
  # backup_pre_shared_key - (optional) is a type of string
  backup_pre_shared_key = null
  # backup_remote_gateway_ip - (optional) is a type of string
  backup_remote_gateway_ip = null
  # backup_remote_lan_ip - (optional) is a type of string
  backup_remote_lan_ip = null
  # backup_remote_tunnel_cidr - (optional) is a type of string
  backup_remote_tunnel_cidr = null
  # bgp_local_as_num - (optional) is a type of string
  bgp_local_as_num = null
  # bgp_remote_as_num - (optional) is a type of string
  bgp_remote_as_num = null
  # connection_name - (required) is a type of string
  connection_name = null
  # connection_type - (optional) is a type of string
  connection_type = null
  # custom_algorithms - (optional) is a type of bool
  custom_algorithms = null
  # direct_connect - (optional) is a type of bool
  direct_connect = null
  # enable_edge_segmentation - (optional) is a type of bool
  enable_edge_segmentation = null
  # enable_ikev2 - (optional) is a type of bool
  enable_ikev2 = null
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = null
  # gw_name - (required) is a type of string
  gw_name = null
  # ha_enabled - (optional) is a type of bool
  ha_enabled = null
  # local_lan_ip - (optional) is a type of string
  local_lan_ip = null
  # local_tunnel_cidr - (optional) is a type of string
  local_tunnel_cidr = null
  # manual_bgp_advertised_cidrs - (optional) is a type of set of string
  manual_bgp_advertised_cidrs = []
  # phase_1_authentication - (optional) is a type of string
  phase_1_authentication = null
  # phase_1_dh_groups - (optional) is a type of string
  phase_1_dh_groups = null
  # phase_1_encryption - (optional) is a type of string
  phase_1_encryption = null
  # phase_2_authentication - (optional) is a type of string
  phase_2_authentication = null
  # phase_2_dh_groups - (optional) is a type of string
  phase_2_dh_groups = null
  # phase_2_encryption - (optional) is a type of string
  phase_2_encryption = null
  # pre_shared_key - (optional) is a type of string
  pre_shared_key = null
  # remote_gateway_ip - (optional) is a type of string
  remote_gateway_ip = null
  # remote_lan_ip - (optional) is a type of string
  remote_lan_ip = null
  # remote_subnet - (optional) is a type of string
  remote_subnet = null
  # remote_tunnel_cidr - (optional) is a type of string
  remote_tunnel_cidr = null
  # remote_vpc_name - (optional) is a type of string
  remote_vpc_name = null
  # switch_to_ha_standby_gateway - (optional) is a type of bool
  switch_to_ha_standby_gateway = null
  # tunnel_protocol - (optional) is a type of string
  tunnel_protocol = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_bgp_remote_as_num" {
  description = "(optional) - Backup BGP remote ASN (Autonomous System Number). Integer between 1-4294967294."
  type        = string
  default     = null
}

variable "backup_direct_connect" {
  description = "(optional) - Backup direct connect for backup external device."
  type        = bool
  default     = null
}

variable "backup_local_lan_ip" {
  description = "(optional) - Backup Local LAN IP."
  type        = string
  default     = null
}

variable "backup_local_tunnel_cidr" {
  description = "(optional) - Source CIDR for the tunnel from the backup Aviatrix transit gateway."
  type        = string
  default     = null
}

variable "backup_pre_shared_key" {
  description = "(optional) - Backup pre shared key."
  type        = string
  default     = null
}

variable "backup_remote_gateway_ip" {
  description = "(optional) - Backup remote gateway IP."
  type        = string
  default     = null
}

variable "backup_remote_lan_ip" {
  description = "(optional) - Backup Remote LAN IP."
  type        = string
  default     = null
}

variable "backup_remote_tunnel_cidr" {
  description = "(optional) - Destination CIDR for the tunnel to the backup external device."
  type        = string
  default     = null
}

variable "bgp_local_as_num" {
  description = "(optional) - BGP local ASN (Autonomous System Number). Integer between 1-4294967294."
  type        = string
  default     = null
}

variable "bgp_remote_as_num" {
  description = "(optional) - BGP remote ASN (Autonomous System Number). Integer between 1-4294967294."
  type        = string
  default     = null
}

variable "connection_name" {
  description = "(required) - The name of the transit external device connection which is going to be created."
  type        = string
}

variable "connection_type" {
  description = "(optional) - Connection type. Valid values: 'bgp', 'static'. Default value: 'bgp'."
  type        = string
  default     = null
}

variable "custom_algorithms" {
  description = "(optional) - Switch to enable custom/non-default algorithms for IPSec Authentication/Encryption."
  type        = bool
  default     = null
}

variable "direct_connect" {
  description = "(optional) - Set true for private network infrastructure."
  type        = bool
  default     = null
}

variable "enable_edge_segmentation" {
  description = "(optional) - Switch to allow this connection to communicate with a Security Domain via Connection Policy."
  type        = bool
  default     = null
}

variable "enable_ikev2" {
  description = "(optional) - Set as true if use IKEv2."
  type        = bool
  default     = null
}

variable "enable_learned_cidrs_approval" {
  description = "(optional) - Enable learned CIDR approval for the connection. Only valid with 'connection_type' = 'bgp'. Requires the transit_gateway's 'learned_cidrs_approval_mode' attribute be set to 'connection'. Valid values: true, false. Default value: false. Available as of provider version R2.18+."
  type        = bool
  default     = null
}

variable "gw_name" {
  description = "(required) - Name of the Transit Gateway."
  type        = string
}

variable "ha_enabled" {
  description = "(optional) - Set as true if there are two external devices."
  type        = bool
  default     = null
}

variable "local_lan_ip" {
  description = "(optional) - Local LAN IP."
  type        = string
  default     = null
}

variable "local_tunnel_cidr" {
  description = "(optional) - Source CIDR for the tunnel from the Aviatrix transit gateway."
  type        = string
  default     = null
}

variable "manual_bgp_advertised_cidrs" {
  description = "(optional) - Configure manual BGP advertised CIDRs for this connection. Only valid with 'connection_type' = 'bgp'. Available as of provider version R2.18+."
  type        = set(string)
  default     = null
}

variable "phase_1_authentication" {
  description = "(optional) - Phase one Authentication. Valid values: 'SHA-1', 'SHA-256', 'SHA-384' and 'SHA-512'."
  type        = string
  default     = null
}

variable "phase_1_dh_groups" {
  description = "(optional) - Phase one DH Groups. Valid values: '1', '2', '5', '14', '15', '16', '17', '18', '19', '20' and '21'."
  type        = string
  default     = null
}

variable "phase_1_encryption" {
  description = "(optional) - Phase one Encryption. Valid values: '3DES', 'AES-128-CBC', 'AES-192-CBC' and 'AES-256-CBC'."
  type        = string
  default     = null
}

variable "phase_2_authentication" {
  description = "(optional) - Phase two Authentication. Valid values: 'NO-AUTH', 'HMAC-SHA-1', 'HMAC-SHA-256', 'HMAC-SHA-384' and 'HMAC-SHA-512'."
  type        = string
  default     = null
}

variable "phase_2_dh_groups" {
  description = "(optional) - Phase two DH Groups. Valid values: '1', '2', '5', '14', '15', '16', '17', '18', '19', '20' and '21'."
  type        = string
  default     = null
}

variable "phase_2_encryption" {
  description = "(optional) - Phase two Encryption. Valid values: '3DES', 'AES-128-CBC', 'AES-192-CBC', 'AES-256-CBC', 'AES-128-GCM-64', 'AES-128-GCM-96' and 'AES-128-GCM-128'."
  type        = string
  default     = null
}

variable "pre_shared_key" {
  description = "(optional) - If left blank, the pre-shared key will be auto generated."
  type        = string
  default     = null
}

variable "remote_gateway_ip" {
  description = "(optional) - Remote Gateway IP."
  type        = string
  default     = null
}

variable "remote_lan_ip" {
  description = "(optional) - Remote LAN IP."
  type        = string
  default     = null
}

variable "remote_subnet" {
  description = "(optional) - Remote CIDRs joined as a string with ','. Required for a 'static' type connection."
  type        = string
  default     = null
}

variable "remote_tunnel_cidr" {
  description = "(optional) - Destination CIDR for the tunnel to the external device."
  type        = string
  default     = null
}

variable "remote_vpc_name" {
  description = "(optional) - Name of the remote VPC for a LAN BGP connection. Only valid when 'connection_type' = 'bgp' and tunnel_protocol' = 'LAN' with an Azure transit gateway. Must be in the form \"<VNET-name>:<resource-group-name>\". Available as of provider version R2.18+."
  type        = string
  default     = null
}

variable "switch_to_ha_standby_gateway" {
  description = "(optional) - Only valid for Transit Gateway's with Active-Standby Mode enabled. Valid values: true, false. Default: false."
  type        = bool
  default     = null
}

variable "tunnel_protocol" {
  description = "(optional) - Tunnel Protocol. Valid values: 'IPsec', 'GRE' or 'LAN'. Default value: 'IPsec'."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the VPC where the Transit Gateway is located."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_transit_external_device_conn" "this" {
  # backup_bgp_remote_as_num - (optional) is a type of string
  backup_bgp_remote_as_num = var.backup_bgp_remote_as_num
  # backup_direct_connect - (optional) is a type of bool
  backup_direct_connect = var.backup_direct_connect
  # backup_local_lan_ip - (optional) is a type of string
  backup_local_lan_ip = var.backup_local_lan_ip
  # backup_local_tunnel_cidr - (optional) is a type of string
  backup_local_tunnel_cidr = var.backup_local_tunnel_cidr
  # backup_pre_shared_key - (optional) is a type of string
  backup_pre_shared_key = var.backup_pre_shared_key
  # backup_remote_gateway_ip - (optional) is a type of string
  backup_remote_gateway_ip = var.backup_remote_gateway_ip
  # backup_remote_lan_ip - (optional) is a type of string
  backup_remote_lan_ip = var.backup_remote_lan_ip
  # backup_remote_tunnel_cidr - (optional) is a type of string
  backup_remote_tunnel_cidr = var.backup_remote_tunnel_cidr
  # bgp_local_as_num - (optional) is a type of string
  bgp_local_as_num = var.bgp_local_as_num
  # bgp_remote_as_num - (optional) is a type of string
  bgp_remote_as_num = var.bgp_remote_as_num
  # connection_name - (required) is a type of string
  connection_name = var.connection_name
  # connection_type - (optional) is a type of string
  connection_type = var.connection_type
  # custom_algorithms - (optional) is a type of bool
  custom_algorithms = var.custom_algorithms
  # direct_connect - (optional) is a type of bool
  direct_connect = var.direct_connect
  # enable_edge_segmentation - (optional) is a type of bool
  enable_edge_segmentation = var.enable_edge_segmentation
  # enable_ikev2 - (optional) is a type of bool
  enable_ikev2 = var.enable_ikev2
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = var.enable_learned_cidrs_approval
  # gw_name - (required) is a type of string
  gw_name = var.gw_name
  # ha_enabled - (optional) is a type of bool
  ha_enabled = var.ha_enabled
  # local_lan_ip - (optional) is a type of string
  local_lan_ip = var.local_lan_ip
  # local_tunnel_cidr - (optional) is a type of string
  local_tunnel_cidr = var.local_tunnel_cidr
  # manual_bgp_advertised_cidrs - (optional) is a type of set of string
  manual_bgp_advertised_cidrs = var.manual_bgp_advertised_cidrs
  # phase_1_authentication - (optional) is a type of string
  phase_1_authentication = var.phase_1_authentication
  # phase_1_dh_groups - (optional) is a type of string
  phase_1_dh_groups = var.phase_1_dh_groups
  # phase_1_encryption - (optional) is a type of string
  phase_1_encryption = var.phase_1_encryption
  # phase_2_authentication - (optional) is a type of string
  phase_2_authentication = var.phase_2_authentication
  # phase_2_dh_groups - (optional) is a type of string
  phase_2_dh_groups = var.phase_2_dh_groups
  # phase_2_encryption - (optional) is a type of string
  phase_2_encryption = var.phase_2_encryption
  # pre_shared_key - (optional) is a type of string
  pre_shared_key = var.pre_shared_key
  # remote_gateway_ip - (optional) is a type of string
  remote_gateway_ip = var.remote_gateway_ip
  # remote_lan_ip - (optional) is a type of string
  remote_lan_ip = var.remote_lan_ip
  # remote_subnet - (optional) is a type of string
  remote_subnet = var.remote_subnet
  # remote_tunnel_cidr - (optional) is a type of string
  remote_tunnel_cidr = var.remote_tunnel_cidr
  # remote_vpc_name - (optional) is a type of string
  remote_vpc_name = var.remote_vpc_name
  # switch_to_ha_standby_gateway - (optional) is a type of bool
  switch_to_ha_standby_gateway = var.switch_to_ha_standby_gateway
  # tunnel_protocol - (optional) is a type of string
  tunnel_protocol = var.tunnel_protocol
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "backup_local_lan_ip" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.backup_local_lan_ip
}

output "backup_local_tunnel_cidr" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.backup_local_tunnel_cidr
}

output "backup_remote_tunnel_cidr" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.backup_remote_tunnel_cidr
}

output "id" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.id
}

output "local_lan_ip" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.local_lan_ip
}

output "local_tunnel_cidr" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.local_tunnel_cidr
}

output "remote_tunnel_cidr" {
  description = "returns a string"
  value       = aviatrix_transit_external_device_conn.this.remote_tunnel_cidr
}

output "this" {
  value = aviatrix_transit_external_device_conn.this
}
```

[top](#index)