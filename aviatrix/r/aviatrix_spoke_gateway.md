# aviatrix_spoke_gateway

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
module "aviatrix_spoke_gateway" {
  source = "./modules/aviatrix/r/aviatrix_spoke_gateway"

  # account_name - (required) is a type of string
  account_name = null
  # allocate_new_eip - (optional) is a type of bool
  allocate_new_eip = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # customer_managed_keys - (optional) is a type of string
  customer_managed_keys = null
  # customized_spoke_vpc_routes - (optional) is a type of string
  customized_spoke_vpc_routes = null
  # eip - (optional) is a type of string
  eip = null
  # enable_active_mesh - (optional) is a type of bool
  enable_active_mesh = null
  # enable_encrypt_volume - (optional) is a type of bool
  enable_encrypt_volume = null
  # enable_vpc_dns_server - (optional) is a type of bool
  enable_vpc_dns_server = null
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
  # included_advertised_spoke_routes - (optional) is a type of string
  included_advertised_spoke_routes = null
  # insane_mode - (optional) is a type of bool
  insane_mode = null
  # insane_mode_az - (optional) is a type of string
  insane_mode_az = null
  # manage_transit_gateway_attachment - (optional) is a type of bool
  manage_transit_gateway_attachment = null
  # single_az_ha - (optional) is a type of bool
  single_az_ha = null
  # single_ip_snat - (optional) is a type of bool
  single_ip_snat = null
  # subnet - (required) is a type of string
  subnet = null
  # tag_list - (optional) is a type of list of string
  tag_list = []
  # transit_gw - (optional) is a type of string
  transit_gw = null
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

variable "cloud_type" {
  description = "(required) - Type of cloud service provider."
  type        = number
}

variable "customer_managed_keys" {
  description = "(optional) - Customer managed key ID."
  type        = string
  default     = null
}

variable "customized_spoke_vpc_routes" {
  description = "(optional) - A list of comma separated CIDRs to be customized for the spoke VPC routes. When configured, it will replace all learned routes in VPC routing tables, including RFC1918 and non-RFC1918 CIDRs. It applies to this spoke gateway only\u200b."
  type        = string
  default     = null
}

variable "eip" {
  description = "(optional) - Required when allocate_new_eip is false. It uses specified EIP for this gateway."
  type        = string
  default     = null
}

variable "enable_active_mesh" {
  description = "(optional) - Switch to Enable/Disable Active Mesh Mode for Spoke Gateway. Valid values: true, false."
  type        = bool
  default     = null
}

variable "enable_encrypt_volume" {
  description = "(optional) - Enable encrypt gateway EBS volume. Only supported for AWS provider. Valid values: true, false. Default value: false."
  type        = bool
  default     = null
}

variable "enable_vpc_dns_server" {
  description = "(optional) - Enable vpc_dns_server for Gateway. Only supports AWS. Valid values: true, false."
  type        = bool
  default     = null
}

variable "filtered_spoke_vpc_routes" {
  description = "(optional) - A list of comma separated CIDRs to be filtered from the spoke VPC route table. When configured, filtering CIDR(s) or it’s subnet will be deleted from VPC routing tables as well as from spoke gateway’s routing table. It applies to this spoke gateway only."
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
  description = "(optional) - Public IP address that you want assigned to the HA Spoke Gateway."
  type        = string
  default     = null
}

variable "ha_gw_size" {
  description = "(optional) - HA Gateway Size."
  type        = string
  default     = null
}

variable "ha_insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Spoke HA Gateway. Required for AWS if insane_mode is true and ha_subnet is set."
  type        = string
  default     = null
}

variable "ha_subnet" {
  description = "(optional) - HA Subnet. Required if enabling HA for AWS/AZURE. Optional if enabling HA for GCP."
  type        = string
  default     = null
}

variable "ha_zone" {
  description = "(optional) - HA Zone. Required if enabling HA for GCP. Optional for Azure."
  type        = string
  default     = null
}

variable "included_advertised_spoke_routes" {
  description = "(optional) - A list of comma separated CIDRs to be advertised to on-prem as 'Included CIDR List'. When configured, it will replace all advertised routes from this VPC.\u200b"
  type        = string
  default     = null
}

variable "insane_mode" {
  description = "(optional) - Enable Insane Mode for Spoke Gateway. Valid values: true, false. If insane mode is enabled, gateway size has to at least be c5 size for AWS and Standard_D3_v2 size for AZURE."
  type        = bool
  default     = null
}

variable "insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Spoke Gateway. Required if insane_mode is enabled for AWS cloud."
  type        = string
  default     = null
}

variable "manage_transit_gateway_attachment" {
  description = "(optional) - This parameter is a switch used to determine whether or not to manage attaching this spoke gateway to transit gateways using the aviatrix_spoke_gateway resource. If this is set to false, attaching this spoke gateway to transit gateways must be done using the aviatrix_spoke_transit_attachment resource. Valid values: true, false. Default value: true."
  type        = bool
  default     = null
}

variable "single_az_ha" {
  description = "(optional) - Set to 'enabled' if this feature is desired."
  type        = bool
  default     = null
}

variable "single_ip_snat" {
  description = "(optional) - Specify whether to enable Source NAT feature in 'single_ip' mode on the gateway or not."
  type        = bool
  default     = null
}

variable "subnet" {
  description = "(required) - Public Subnet Info."
  type        = string
}

variable "tag_list" {
  description = "(optional) - Instance tag of cloud provider."
  type        = list(string)
  default     = null
}

variable "transit_gw" {
  description = "(optional) - Specify the transit Gateways to attach to this spoke. Format is a comma-separated list of transit gateway names. For example, 'transit-gw1,transit-gw2'."
  type        = string
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
resource "aviatrix_spoke_gateway" "this" {
  account_name                      = var.account_name
  allocate_new_eip                  = var.allocate_new_eip
  cloud_type                        = var.cloud_type
  customer_managed_keys             = var.customer_managed_keys
  customized_spoke_vpc_routes       = var.customized_spoke_vpc_routes
  eip                               = var.eip
  enable_active_mesh                = var.enable_active_mesh
  enable_encrypt_volume             = var.enable_encrypt_volume
  enable_vpc_dns_server             = var.enable_vpc_dns_server
  filtered_spoke_vpc_routes         = var.filtered_spoke_vpc_routes
  gw_name                           = var.gw_name
  gw_size                           = var.gw_size
  ha_eip                            = var.ha_eip
  ha_gw_size                        = var.ha_gw_size
  ha_insane_mode_az                 = var.ha_insane_mode_az
  ha_subnet                         = var.ha_subnet
  ha_zone                           = var.ha_zone
  included_advertised_spoke_routes  = var.included_advertised_spoke_routes
  insane_mode                       = var.insane_mode
  insane_mode_az                    = var.insane_mode_az
  manage_transit_gateway_attachment = var.manage_transit_gateway_attachment
  single_az_ha                      = var.single_az_ha
  single_ip_snat                    = var.single_ip_snat
  subnet                            = var.subnet
  tag_list                          = var.tag_list
  transit_gw                        = var.transit_gw
  vpc_id                            = var.vpc_id
  vpc_reg                           = var.vpc_reg
  zone                              = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.cloud_instance_id
}

output "eip" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.eip
}

output "ha_cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.ha_cloud_instance_id
}

output "ha_eip" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.ha_eip
}

output "ha_gw_name" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.ha_gw_name
}

output "ha_private_ip" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.ha_private_ip
}

output "id" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.id
}

output "private_ip" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.private_ip
}

output "security_group_id" {
  description = "returns a string"
  value       = aviatrix_spoke_gateway.this.security_group_id
}

output "this" {
  value = aviatrix_spoke_gateway.this
}
```

[top](#index)