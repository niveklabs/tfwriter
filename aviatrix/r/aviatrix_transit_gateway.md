# aviatrix_transit_gateway

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
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_transit_gateway" {
  source = "./modules/aviatrix/r/aviatrix_transit_gateway"

  # account_name - (required) is a type of string
  account_name = null
  # allocate_new_eip - (optional) is a type of bool
  allocate_new_eip = null
  # bgp_ecmp - (optional) is a type of bool
  bgp_ecmp = null
  # bgp_manual_spoke_advertise_cidrs - (optional) is a type of string
  bgp_manual_spoke_advertise_cidrs = null
  # bgp_polling_time - (optional) is a type of string
  bgp_polling_time = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # connected_transit - (optional) is a type of bool
  connected_transit = null
  # customer_managed_keys - (optional) is a type of string
  customer_managed_keys = null
  # customized_spoke_vpc_routes - (optional) is a type of string
  customized_spoke_vpc_routes = null
  # eip - (optional) is a type of string
  eip = null
  # enable_active_mesh - (optional) is a type of bool
  enable_active_mesh = null
  # enable_active_standby - (optional) is a type of bool
  enable_active_standby = null
  # enable_advertise_transit_cidr - (optional) is a type of bool
  enable_advertise_transit_cidr = null
  # enable_egress_transit_firenet - (optional) is a type of bool
  enable_egress_transit_firenet = null
  # enable_encrypt_volume - (optional) is a type of bool
  enable_encrypt_volume = null
  # enable_firenet - (optional) is a type of bool
  enable_firenet = null
  # enable_hybrid_connection - (optional) is a type of bool
  enable_hybrid_connection = null
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = null
  # enable_segmentation - (optional) is a type of bool
  enable_segmentation = null
  # enable_transit_firenet - (optional) is a type of bool
  enable_transit_firenet = null
  # enable_vpc_dns_server - (optional) is a type of bool
  enable_vpc_dns_server = null
  # excluded_advertised_spoke_routes - (optional) is a type of string
  excluded_advertised_spoke_routes = null
  # filtered_spoke_vpc_routes - (optional) is a type of string
  filtered_spoke_vpc_routes = null
  # gw_name - (required) is a type of string
  gw_name = null
  # gw_size - (required) is a type of string
  gw_size = null
  # ha_eip - (optional) is a type of string
  ha_eip = null
  # ha_gw_size - (optional) is a type of string
  ha_gw_size = null
  # ha_insane_mode_az - (optional) is a type of string
  ha_insane_mode_az = null
  # ha_subnet - (optional) is a type of string
  ha_subnet = null
  # ha_zone - (optional) is a type of string
  ha_zone = null
  # insane_mode - (optional) is a type of bool
  insane_mode = null
  # insane_mode_az - (optional) is a type of string
  insane_mode_az = null
  # local_as_number - (optional) is a type of string
  local_as_number = null
  # prepend_as_path - (optional) is a type of list of string
  prepend_as_path = []
  # single_az_ha - (optional) is a type of bool
  single_az_ha = null
  # single_ip_snat - (optional) is a type of bool
  single_ip_snat = null
  # subnet - (required) is a type of string
  subnet = null
  # tag_list - (optional) is a type of list of string
  tag_list = []
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vpc_reg - (required) is a type of string
  vpc_reg = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
}

variable "allocate_new_eip" {
  description = "(optional) - If false, reuse an idle address in Elastic IP pool for this gateway. Otherwise, allocate a new Elastic IP and use it for this gateway."
  type        = bool
  default     = null
}

variable "bgp_ecmp" {
  description = "(optional) - Enable Equal Cost Multi Path (ECMP) routing for the next hop."
  type        = bool
  default     = null
}

variable "bgp_manual_spoke_advertise_cidrs" {
  description = "(optional) - Intended CIDR list to advertise to VGW."
  type        = string
  default     = null
}

variable "bgp_polling_time" {
  description = "(optional) - BGP route polling time. Unit is in seconds. Valid values are between 10 and 50."
  type        = string
  default     = null
}

variable "cloud_type" {
  description = "(required) - Type of cloud service provider, requires an integer value. Use 1 for AWS."
  type        = number
}

variable "connected_transit" {
  description = "(optional) - Specify Connected Transit status."
  type        = bool
  default     = null
}

variable "customer_managed_keys" {
  description = "(optional) - Customer managed key ID."
  type        = string
  default     = null
}

variable "customized_spoke_vpc_routes" {
  description = "(optional) - A list of comma separated CIDRs to be customized for the spoke VPC routes. When configured, it will replace all learned routes in VPC routing tables, including RFC1918 and non-RFC1918 CIDRs. It applies to all spoke gateways attached to this transit gateway."
  type        = string
  default     = null
}

variable "eip" {
  description = "(optional) - Required when allocate_new_eip is false. It uses specified EIP for this gateway."
  type        = string
  default     = null
}

variable "enable_active_mesh" {
  description = "(optional) - Switch to Enable/Disable Active Mesh Mode for Transit Gateway. Valid values: true, false."
  type        = bool
  default     = null
}

variable "enable_active_standby" {
  description = "(optional) - Enables Active-Standby Mode, available only with Active Mesh Mode and HA enabled."
  type        = bool
  default     = null
}

variable "enable_advertise_transit_cidr" {
  description = "(optional) - Switch to Enable/Disable advertise transit VPC network CIDR."
  type        = bool
  default     = null
}

variable "enable_egress_transit_firenet" {
  description = "(optional) - Specify whether to enable egress transit firenet interfaces or not."
  type        = bool
  default     = null
}

variable "enable_encrypt_volume" {
  description = "(optional) - Enable encrypt gateway EBS volume. Only supported for AWS and AWSGOV providers. Valid values: true, false. Default value: false."
  type        = bool
  default     = null
}

variable "enable_firenet" {
  description = "(optional) - Specify whether to enable firenet interfaces or not."
  type        = bool
  default     = null
}

variable "enable_hybrid_connection" {
  description = "(optional) - Sign of readiness for TGW connection."
  type        = bool
  default     = null
}

variable "enable_learned_cidrs_approval" {
  description = "(optional) - Switch to enable/disable encrypted transit approval for transit Gateway. Valid values: true, false."
  type        = bool
  default     = null
}

variable "enable_segmentation" {
  description = "(optional) - Enable segmentation to allow association of transit gateway to security domains."
  type        = bool
  default     = null
}

variable "enable_transit_firenet" {
  description = "(optional) - Specify whether to enable transit firenet interfaces or not."
  type        = bool
  default     = null
}

variable "enable_vpc_dns_server" {
  description = "(optional) - Enable vpc_dns_server for Gateway. Only supports AWS/AWSGOV. Valid values: true, false."
  type        = bool
  default     = null
}

variable "excluded_advertised_spoke_routes" {
  description = "(optional) - A list of comma separated CIDRs to be advertised to on-prem as 'Excluded CIDR List'. When configured, it inspects all the advertised CIDRs from its spoke gateways and remove those included in the 'Excluded CIDR List'."
  type        = string
  default     = null
}

variable "filtered_spoke_vpc_routes" {
  description = "(optional) - A list of comma separated CIDRs to be filtered from the spoke VPC route table. When configured, filtering CIDR(s) or it’s subnet will be deleted from VPC routing tables as well as from spoke gateway’s routing table. It applies to all spoke gateways attached to this transit gateway."
  type        = string
  default     = null
}

variable "gw_name" {
  description = "(required) - Name of the gateway which is going to be created."
  type        = string
}

variable "gw_size" {
  description = "(required) - Size of the gateway instance."
  type        = string
}

variable "ha_eip" {
  description = "(optional) - Public IP address that you want assigned to the HA Transit Gateway."
  type        = string
  default     = null
}

variable "ha_gw_size" {
  description = "(optional) - HA Gateway Size. Mandatory if HA is enabled (ha_subnet is set)."
  type        = string
  default     = null
}

variable "ha_insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Transit HA Gateway. Required for AWS if insane_mode is enabled and ha_subnet is set."
  type        = string
  default     = null
}

variable "ha_subnet" {
  description = "(optional) - HA Subnet. Required for enabling HA for AWS/AZURE/AWSGOV gateway. Optional for enabling HA for GCP gateway."
  type        = string
  default     = null
}

variable "ha_zone" {
  description = "(optional) - HA Zone. Required if enabling HA for GCP. Optional for AZURE."
  type        = string
  default     = null
}

variable "insane_mode" {
  description = "(optional) - Enable Insane Mode for Transit. Valid values: true, false. If insane mode is enabled, gateway size has to at least be c5 size for AWS and Standard_D3_v2 size for AZURE."
  type        = bool
  default     = null
}

variable "insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Transit Gateway. Required for AWS if insane_mode is enabled."
  type        = string
  default     = null
}

variable "local_as_number" {
  description = "(optional) - Changes the Aviatrix Transit Gateway ASN number before you setup Aviatrix Transit Gateway connection configurations."
  type        = string
  default     = null
}

variable "prepend_as_path" {
  description = "(optional) - List of AS numbers to populate BGP AP_PATH field when it advertises to VGW or peer devices."
  type        = list(string)
  default     = null
}

variable "single_az_ha" {
  description = "(optional) - Set to 'enabled' if this feature is desired."
  type        = bool
  default     = null
}

variable "single_ip_snat" {
  description = "(optional) - Enable or disable Source NAT feature in 'single_ip' mode for this container."
  type        = bool
  default     = null
}

variable "subnet" {
  description = "(required) - Public Subnet Name."
  type        = string
}

variable "tag_list" {
  description = "(optional) - Instance tag of cloud provider."
  type        = list(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - VPC-ID/VNet-Name of cloud provider."
  type        = string
}

variable "vpc_reg" {
  description = "(required) - Region of cloud provider."
  type        = string
}

variable "zone" {
  description = "(optional) - Availability Zone. Only available for cloud_type = 8 (AZURE). Must be in the form 'az-n', for example, 'az-2'."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_transit_gateway" "this" {
  account_name                     = var.account_name
  allocate_new_eip                 = var.allocate_new_eip
  bgp_ecmp                         = var.bgp_ecmp
  bgp_manual_spoke_advertise_cidrs = var.bgp_manual_spoke_advertise_cidrs
  bgp_polling_time                 = var.bgp_polling_time
  cloud_type                       = var.cloud_type
  connected_transit                = var.connected_transit
  customer_managed_keys            = var.customer_managed_keys
  customized_spoke_vpc_routes      = var.customized_spoke_vpc_routes
  eip                              = var.eip
  enable_active_mesh               = var.enable_active_mesh
  enable_active_standby            = var.enable_active_standby
  enable_advertise_transit_cidr    = var.enable_advertise_transit_cidr
  enable_egress_transit_firenet    = var.enable_egress_transit_firenet
  enable_encrypt_volume            = var.enable_encrypt_volume
  enable_firenet                   = var.enable_firenet
  enable_hybrid_connection         = var.enable_hybrid_connection
  enable_learned_cidrs_approval    = var.enable_learned_cidrs_approval
  enable_segmentation              = var.enable_segmentation
  enable_transit_firenet           = var.enable_transit_firenet
  enable_vpc_dns_server            = var.enable_vpc_dns_server
  excluded_advertised_spoke_routes = var.excluded_advertised_spoke_routes
  filtered_spoke_vpc_routes        = var.filtered_spoke_vpc_routes
  gw_name                          = var.gw_name
  gw_size                          = var.gw_size
  ha_eip                           = var.ha_eip
  ha_gw_size                       = var.ha_gw_size
  ha_insane_mode_az                = var.ha_insane_mode_az
  ha_subnet                        = var.ha_subnet
  ha_zone                          = var.ha_zone
  insane_mode                      = var.insane_mode
  insane_mode_az                   = var.insane_mode_az
  local_as_number                  = var.local_as_number
  prepend_as_path                  = var.prepend_as_path
  single_az_ha                     = var.single_az_ha
  single_ip_snat                   = var.single_ip_snat
  subnet                           = var.subnet
  tag_list                         = var.tag_list
  vpc_id                           = var.vpc_id
  vpc_reg                          = var.vpc_reg
  zone                             = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.cloud_instance_id
}

output "eip" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.eip
}

output "ha_cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.ha_cloud_instance_id
}

output "ha_eip" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.ha_eip
}

output "ha_gw_name" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.ha_gw_name
}

output "ha_private_ip" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.ha_private_ip
}

output "id" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.id
}

output "lan_interface_cidr" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.lan_interface_cidr
}

output "private_ip" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.private_ip
}

output "security_group_id" {
  description = "returns a string"
  value       = aviatrix_transit_gateway.this.security_group_id
}

output "this" {
  value = aviatrix_transit_gateway.this
}
```

[top](#index)