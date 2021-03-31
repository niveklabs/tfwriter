# aviatrix_site2cloud

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
module "aviatrix_site2cloud" {
  source = "./modules/aviatrix/r/aviatrix_site2cloud"

  # backup_gateway_name - (optional) is a type of string
  backup_gateway_name = null
  # backup_pre_shared_key - (optional) is a type of string
  backup_pre_shared_key = null
  # backup_remote_gateway_ip - (optional) is a type of string
  backup_remote_gateway_ip = null
  # backup_remote_gateway_latitude - (optional) is a type of number
  backup_remote_gateway_latitude = null
  # backup_remote_gateway_longitude - (optional) is a type of number
  backup_remote_gateway_longitude = null
  # connection_name - (required) is a type of string
  connection_name = null
  # connection_type - (required) is a type of string
  connection_type = null
  # custom_algorithms - (optional) is a type of bool
  custom_algorithms = null
  # custom_mapped - (optional) is a type of bool
  custom_mapped = null
  # enable_active_active - (optional) is a type of bool
  enable_active_active = null
  # enable_dead_peer_detection - (optional) is a type of bool
  enable_dead_peer_detection = null
  # enable_ikev2 - (optional) is a type of bool
  enable_ikev2 = null
  # forward_traffic_to_transit - (optional) is a type of bool
  forward_traffic_to_transit = null
  # ha_enabled - (optional) is a type of bool
  ha_enabled = null
  # local_destination_real_cidrs - (optional) is a type of list of string
  local_destination_real_cidrs = []
  # local_destination_virtual_cidrs - (optional) is a type of list of string
  local_destination_virtual_cidrs = []
  # local_source_real_cidrs - (optional) is a type of list of string
  local_source_real_cidrs = []
  # local_source_virtual_cidrs - (optional) is a type of list of string
  local_source_virtual_cidrs = []
  # local_subnet_cidr - (optional) is a type of string
  local_subnet_cidr = null
  # local_subnet_virtual - (optional) is a type of string
  local_subnet_virtual = null
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
  # primary_cloud_gateway_name - (required) is a type of string
  primary_cloud_gateway_name = null
  # private_route_encryption - (optional) is a type of bool
  private_route_encryption = null
  # remote_destination_real_cidrs - (optional) is a type of list of string
  remote_destination_real_cidrs = []
  # remote_destination_virtual_cidrs - (optional) is a type of list of string
  remote_destination_virtual_cidrs = []
  # remote_gateway_ip - (required) is a type of string
  remote_gateway_ip = null
  # remote_gateway_latitude - (optional) is a type of number
  remote_gateway_latitude = null
  # remote_gateway_longitude - (optional) is a type of number
  remote_gateway_longitude = null
  # remote_gateway_type - (required) is a type of string
  remote_gateway_type = null
  # remote_source_real_cidrs - (optional) is a type of list of string
  remote_source_real_cidrs = []
  # remote_source_virtual_cidrs - (optional) is a type of list of string
  remote_source_virtual_cidrs = []
  # remote_subnet_cidr - (optional) is a type of string
  remote_subnet_cidr = null
  # remote_subnet_virtual - (optional) is a type of string
  remote_subnet_virtual = null
  # route_table_list - (optional) is a type of list of string
  route_table_list = []
  # ssl_server_pool - (optional) is a type of string
  ssl_server_pool = null
  # tunnel_type - (required) is a type of string
  tunnel_type = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_gateway_name" {
  description = "(optional) - Backup gateway name."
  type        = string
  default     = null
}

variable "backup_pre_shared_key" {
  description = "(optional) - Backup Pre-Shared Key."
  type        = string
  default     = null
}

variable "backup_remote_gateway_ip" {
  description = "(optional) - Backup remote remote gateway IP."
  type        = string
  default     = null
}

variable "backup_remote_gateway_latitude" {
  description = "(optional) - Latitude of backup remote gateway."
  type        = number
  default     = null
}

variable "backup_remote_gateway_longitude" {
  description = "(optional) - Longitude of backup remote gateway."
  type        = number
  default     = null
}

variable "connection_name" {
  description = "(required) - Site2Cloud Connection Name."
  type        = string
}

variable "connection_type" {
  description = "(required) - Connection Type. Valid values: 'mapped' and 'unmapped'."
  type        = string
}

variable "custom_algorithms" {
  description = "(optional) - Switch to enable custom/non-default algorithms for IPSec Authentication/Encryption."
  type        = bool
  default     = null
}

variable "custom_mapped" {
  description = "(optional) - Enable custom mapped."
  type        = bool
  default     = null
}

variable "enable_active_active" {
  description = "(optional) - Switch to Enable/Disable active_active_ha for an existing site2cloud connection."
  type        = bool
  default     = null
}

variable "enable_dead_peer_detection" {
  description = "(optional) - Switch to Enable/Disable Deed Peer Detection for an existing site2cloud connection."
  type        = bool
  default     = null
}

variable "enable_ikev2" {
  description = "(optional) - Switch to enable IKEv2 for policy based site2cloud."
  type        = bool
  default     = null
}

variable "forward_traffic_to_transit" {
  description = "(optional) - Enable spoke gateway with mapped site2cloud configurations to forward traffic from site2cloud connection to Aviatrix Transit Gateway."
  type        = bool
  default     = null
}

variable "ha_enabled" {
  description = "(optional) - Specify whether enabling HA or not."
  type        = bool
  default     = null
}

variable "local_destination_real_cidrs" {
  description = "(optional) - Local Initiated Traffic Destination Real CIDRs."
  type        = list(string)
  default     = null
}

variable "local_destination_virtual_cidrs" {
  description = "(optional) - Local Initiated Traffic Destination Virtual CIDRs."
  type        = list(string)
  default     = null
}

variable "local_source_real_cidrs" {
  description = "(optional) - Local Initiated Traffic Source Real CIDRs."
  type        = list(string)
  default     = null
}

variable "local_source_virtual_cidrs" {
  description = "(optional) - Local Initiated Traffic Source Virtual CIDRs."
  type        = list(string)
  default     = null
}

variable "local_subnet_cidr" {
  description = "(optional) - Local Subnet CIDR."
  type        = string
  default     = null
}

variable "local_subnet_virtual" {
  description = "(optional) - Local Subnet CIDR (Virtual)."
  type        = string
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
  description = "(optional) - Phase two Encryption. Valid values: '3DES', 'AES-128-CBC', 'AES-192-CBC', 'AES-256-CBC', 'AES-128-GCM-64', 'AES-128-GCM-96', 'AES-128-GCM-128', and 'NULL-ENCR'."
  type        = string
  default     = null
}

variable "pre_shared_key" {
  description = "(optional) - Pre-Shared Key."
  type        = string
  default     = null
}

variable "primary_cloud_gateway_name" {
  description = "(required) - Primary Cloud Gateway Name."
  type        = string
}

variable "private_route_encryption" {
  description = "(optional) - Private route encryption switch."
  type        = bool
  default     = null
}

variable "remote_destination_real_cidrs" {
  description = "(optional) - Remote Initiated Traffic Destination Real CIDRs."
  type        = list(string)
  default     = null
}

variable "remote_destination_virtual_cidrs" {
  description = "(optional) - Remote Initiated Traffic Destination Virtual CIDRs."
  type        = list(string)
  default     = null
}

variable "remote_gateway_ip" {
  description = "(required) - Remote Gateway IP."
  type        = string
}

variable "remote_gateway_latitude" {
  description = "(optional) - Latitude of remote gateway."
  type        = number
  default     = null
}

variable "remote_gateway_longitude" {
  description = "(optional) - Longitude of remote gateway."
  type        = number
  default     = null
}

variable "remote_gateway_type" {
  description = "(required) - Remote gateway type. Valid values: 'generic', 'avx', 'aws', 'azure', 'sonicwall' and 'oracle'."
  type        = string
}

variable "remote_source_real_cidrs" {
  description = "(optional) - Remote Initiated Traffic Source Real CIDRs."
  type        = list(string)
  default     = null
}

variable "remote_source_virtual_cidrs" {
  description = "(optional) - Remote Initiated Traffic Source Virtual CIDRs."
  type        = list(string)
  default     = null
}

variable "remote_subnet_cidr" {
  description = "(optional) - Remote Subnet CIDR."
  type        = string
  default     = null
}

variable "remote_subnet_virtual" {
  description = "(optional) - Remote Subnet CIDR (Virtual)."
  type        = string
  default     = null
}

variable "route_table_list" {
  description = "(optional) - Route tables to modify."
  type        = list(string)
  default     = null
}

variable "ssl_server_pool" {
  description = "(optional) - Specify ssl_server_pool for tunnel_type 'tcp'. Default value is '192.168.44.0/24'"
  type        = string
  default     = null
}

variable "tunnel_type" {
  description = "(required) - Site2Cloud Tunnel Type. Valid values: 'policy' and 'route'."
  type        = string
}

variable "vpc_id" {
  description = "(required) - VPC Id of the cloud gateway."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_site2cloud" "this" {
  backup_gateway_name              = var.backup_gateway_name
  backup_pre_shared_key            = var.backup_pre_shared_key
  backup_remote_gateway_ip         = var.backup_remote_gateway_ip
  backup_remote_gateway_latitude   = var.backup_remote_gateway_latitude
  backup_remote_gateway_longitude  = var.backup_remote_gateway_longitude
  connection_name                  = var.connection_name
  connection_type                  = var.connection_type
  custom_algorithms                = var.custom_algorithms
  custom_mapped                    = var.custom_mapped
  enable_active_active             = var.enable_active_active
  enable_dead_peer_detection       = var.enable_dead_peer_detection
  enable_ikev2                     = var.enable_ikev2
  forward_traffic_to_transit       = var.forward_traffic_to_transit
  ha_enabled                       = var.ha_enabled
  local_destination_real_cidrs     = var.local_destination_real_cidrs
  local_destination_virtual_cidrs  = var.local_destination_virtual_cidrs
  local_source_real_cidrs          = var.local_source_real_cidrs
  local_source_virtual_cidrs       = var.local_source_virtual_cidrs
  local_subnet_cidr                = var.local_subnet_cidr
  local_subnet_virtual             = var.local_subnet_virtual
  phase_1_authentication           = var.phase_1_authentication
  phase_1_dh_groups                = var.phase_1_dh_groups
  phase_1_encryption               = var.phase_1_encryption
  phase_2_authentication           = var.phase_2_authentication
  phase_2_dh_groups                = var.phase_2_dh_groups
  phase_2_encryption               = var.phase_2_encryption
  pre_shared_key                   = var.pre_shared_key
  primary_cloud_gateway_name       = var.primary_cloud_gateway_name
  private_route_encryption         = var.private_route_encryption
  remote_destination_real_cidrs    = var.remote_destination_real_cidrs
  remote_destination_virtual_cidrs = var.remote_destination_virtual_cidrs
  remote_gateway_ip                = var.remote_gateway_ip
  remote_gateway_latitude          = var.remote_gateway_latitude
  remote_gateway_longitude         = var.remote_gateway_longitude
  remote_gateway_type              = var.remote_gateway_type
  remote_source_real_cidrs         = var.remote_source_real_cidrs
  remote_source_virtual_cidrs      = var.remote_source_virtual_cidrs
  remote_subnet_cidr               = var.remote_subnet_cidr
  remote_subnet_virtual            = var.remote_subnet_virtual
  route_table_list                 = var.route_table_list
  ssl_server_pool                  = var.ssl_server_pool
  tunnel_type                      = var.tunnel_type
  vpc_id                           = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_site2cloud.this.id
}

output "local_subnet_cidr" {
  description = "returns a string"
  value       = aviatrix_site2cloud.this.local_subnet_cidr
}

output "this" {
  value = aviatrix_site2cloud.this
}
```

[top](#index)