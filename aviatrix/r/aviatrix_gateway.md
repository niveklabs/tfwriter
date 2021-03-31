# aviatrix_gateway

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
module "aviatrix_gateway" {
  source = "./modules/aviatrix/r/aviatrix_gateway"

  # account_name - (required) is a type of string
  account_name = null
  # additional_cidrs - (optional) is a type of string
  additional_cidrs = null
  # additional_cidrs_designated_gateway - (optional) is a type of string
  additional_cidrs_designated_gateway = null
  # allocate_new_eip - (optional) is a type of bool
  allocate_new_eip = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # customer_managed_keys - (optional) is a type of string
  customer_managed_keys = null
  # duo_api_hostname - (optional) is a type of string
  duo_api_hostname = null
  # duo_integration_key - (optional) is a type of string
  duo_integration_key = null
  # duo_push_mode - (optional) is a type of string
  duo_push_mode = null
  # duo_secret_key - (optional) is a type of string
  duo_secret_key = null
  # eip - (optional) is a type of string
  eip = null
  # elb_name - (optional) is a type of string
  elb_name = null
  # enable_designated_gateway - (optional) is a type of bool
  enable_designated_gateway = null
  # enable_elb - (optional) is a type of bool
  enable_elb = null
  # enable_encrypt_volume - (optional) is a type of bool
  enable_encrypt_volume = null
  # enable_jumbo_frame - (optional) is a type of bool
  enable_jumbo_frame = null
  # enable_ldap - (optional) is a type of bool
  enable_ldap = null
  # enable_monitor_gateway_subnets - (optional) is a type of bool
  enable_monitor_gateway_subnets = null
  # enable_public_subnet_filtering - (optional) is a type of bool
  enable_public_subnet_filtering = null
  # enable_vpc_dns_server - (optional) is a type of bool
  enable_vpc_dns_server = null
  # enable_vpn_nat - (optional) is a type of bool
  enable_vpn_nat = null
  # fqdn_lan_cidr - (optional) is a type of string
  fqdn_lan_cidr = null
  # fqdn_lan_vpc_id - (optional) is a type of string
  fqdn_lan_vpc_id = null
  # gw_name - (required) is a type of string
  gw_name = null
  # gw_size - (required) is a type of string
  gw_size = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # insane_mode - (optional) is a type of bool
  insane_mode = null
  # insane_mode_az - (optional) is a type of string
  insane_mode_az = null
  # ldap_base_dn - (optional) is a type of string
  ldap_base_dn = null
  # ldap_bind_dn - (optional) is a type of string
  ldap_bind_dn = null
  # ldap_password - (optional) is a type of string
  ldap_password = null
  # ldap_server - (optional) is a type of string
  ldap_server = null
  # ldap_username_attribute - (optional) is a type of string
  ldap_username_attribute = null
  # max_vpn_conn - (optional) is a type of string
  max_vpn_conn = null
  # monitor_exclude_list - (optional) is a type of set of string
  monitor_exclude_list = []
  # name_servers - (optional) is a type of string
  name_servers = null
  # okta_token - (optional) is a type of string
  okta_token = null
  # okta_url - (optional) is a type of string
  okta_url = null
  # okta_username_suffix - (optional) is a type of string
  okta_username_suffix = null
  # otp_mode - (optional) is a type of string
  otp_mode = null
  # peering_ha_eip - (optional) is a type of string
  peering_ha_eip = null
  # peering_ha_gw_size - (optional) is a type of string
  peering_ha_gw_size = null
  # peering_ha_insane_mode_az - (optional) is a type of string
  peering_ha_insane_mode_az = null
  # peering_ha_subnet - (optional) is a type of string
  peering_ha_subnet = null
  # peering_ha_zone - (optional) is a type of string
  peering_ha_zone = null
  # public_subnet_filtering_guard_duty_enforced - (optional) is a type of bool
  public_subnet_filtering_guard_duty_enforced = null
  # public_subnet_filtering_ha_route_tables - (optional) is a type of set of string
  public_subnet_filtering_ha_route_tables = []
  # public_subnet_filtering_route_tables - (optional) is a type of set of string
  public_subnet_filtering_route_tables = []
  # renegotiation_interval - (optional) is a type of number
  renegotiation_interval = null
  # saml_enabled - (optional) is a type of bool
  saml_enabled = null
  # search_domains - (optional) is a type of string
  search_domains = null
  # single_az_ha - (optional) is a type of bool
  single_az_ha = null
  # single_ip_snat - (optional) is a type of bool
  single_ip_snat = null
  # split_tunnel - (optional) is a type of bool
  split_tunnel = null
  # subnet - (required) is a type of string
  subnet = null
  # tag_list - (optional) is a type of list of string
  tag_list = []
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vpc_reg - (required) is a type of string
  vpc_reg = null
  # vpn_access - (optional) is a type of bool
  vpn_access = null
  # vpn_cidr - (optional) is a type of string
  vpn_cidr = null
  # vpn_protocol - (optional) is a type of string
  vpn_protocol = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Account name. This account will be used to launch Aviatrix gateway."
  type        = string
}

variable "additional_cidrs" {
  description = "(optional) - A list of destination CIDR ranges that will also go through the VPN tunnel when Split Tunnel Mode is enabled."
  type        = string
  default     = null
}

variable "additional_cidrs_designated_gateway" {
  description = "(optional) - A list of CIDR ranges separated by comma to configure when 'designated_gateway' feature is enabled."
  type        = string
  default     = null
}

variable "allocate_new_eip" {
  description = "(optional) - When value is false, reuse an idle address in Elastic IP pool for this gateway. Otherwise, allocate a new Elastic IP and use it for this gateway."
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

variable "duo_api_hostname" {
  description = "(optional) - API hostname for DUO auth mode."
  type        = string
  default     = null
}

variable "duo_integration_key" {
  description = "(optional) - Integration key for DUO auth mode."
  type        = string
  default     = null
}

variable "duo_push_mode" {
  description = "(optional) - Push mode for DUO auth."
  type        = string
  default     = null
}

variable "duo_secret_key" {
  description = "(optional) - Secret key for DUO auth mode."
  type        = string
  default     = null
}

variable "eip" {
  description = "(optional) - Required when allocate_new_eip is false. It uses specified EIP for this gateway."
  type        = string
  default     = null
}

variable "elb_name" {
  description = "(optional) - A name for the ELB that is created."
  type        = string
  default     = null
}

variable "enable_designated_gateway" {
  description = "(optional) - Enable 'designated_gateway' feature for Gateway. Only supports AWS and AWSGOV. Valid values: true, false."
  type        = bool
  default     = null
}

variable "enable_elb" {
  description = "(optional) - Specify whether to enable ELB or not."
  type        = bool
  default     = null
}

variable "enable_encrypt_volume" {
  description = "(optional) - Enable encrypt gateway EBS volume. Only supported for AWS provider. Valid values: true, false. Default value: false."
  type        = bool
  default     = null
}

variable "enable_jumbo_frame" {
  description = "(optional) - Enable jumbo frame support for Gateway. Valid values: true or false. Default value: true."
  type        = bool
  default     = null
}

variable "enable_ldap" {
  description = "(optional) - Specify whether to enable LDAP or not. Supported values: 'yes' and 'no'."
  type        = bool
  default     = null
}

variable "enable_monitor_gateway_subnets" {
  description = "(optional) - Enable monitor gateway subnets. Valid values: true, false. Default value: false."
  type        = bool
  default     = null
}

variable "enable_public_subnet_filtering" {
  description = "(optional) - Create a [Public Subnet Filtering gateway](https://docs.aviatrix.com/HowTos/public_subnet_filtering_faq.html)."
  type        = bool
  default     = null
}

variable "enable_vpc_dns_server" {
  description = "(optional) - Enable vpc_dns_server for Gateway. Only supports AWS. Valid values: true, false."
  type        = bool
  default     = null
}

variable "enable_vpn_nat" {
  description = "(optional) - This field indicates whether to enable VPN NAT or not. Only supported for VPN gateway. Valid values: true, false. Default value: true."
  type        = bool
  default     = null
}

variable "fqdn_lan_cidr" {
  description = "(optional) - FQDN gateway lan interface cidr."
  type        = string
  default     = null
}

variable "fqdn_lan_vpc_id" {
  description = "(optional) - LAN VPC ID. Only used for GCP FQDN Gateway."
  type        = string
  default     = null
}

variable "gw_name" {
  description = "(required) - Aviatrix gateway unique name."
  type        = string
}

variable "gw_size" {
  description = "(required) - Size of Gateway Instance."
  type        = string
}

variable "idle_timeout" {
  description = "(optional) - Typed value when modifying idle_timeout. If it's -1, this feature is disabled."
  type        = number
  default     = null
}

variable "insane_mode" {
  description = "(optional) - Enable Insane Mode for Gateway. Valid values: true, false."
  type        = bool
  default     = null
}

variable "insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Gateway. Required if insane_mode is set."
  type        = string
  default     = null
}

variable "ldap_base_dn" {
  description = "(optional) - LDAP base DN. Required: Yes if enable_ldap is 'yes'."
  type        = string
  default     = null
}

variable "ldap_bind_dn" {
  description = "(optional) - LDAP bind DN. Required: Yes if enable_ldap is 'yes'."
  type        = string
  default     = null
}

variable "ldap_password" {
  description = "(optional) - LDAP password. Required: Yes if enable_ldap is 'yes'."
  type        = string
  default     = null
}

variable "ldap_server" {
  description = "(optional) - LDAP server address. Required: Yes if enable_ldap is 'yes'."
  type        = string
  default     = null
}

variable "ldap_username_attribute" {
  description = "(optional) - LDAP user attribute. Required: Yes if enable_ldap is 'yes'."
  type        = string
  default     = null
}

variable "max_vpn_conn" {
  description = "(optional) - Maximum connection of VPN access."
  type        = string
  default     = null
}

variable "monitor_exclude_list" {
  description = "(optional) - A set of monitored instance ids. Only valid when 'enable_monitor_gateway_subnets' = true."
  type        = set(string)
  default     = null
}

variable "name_servers" {
  description = "(optional) - A list of DNS servers used to resolve domain names by a connected VPN user when Split Tunnel Mode is enabled."
  type        = string
  default     = null
}

variable "okta_token" {
  description = "(optional) - Token for Okta auth mode."
  type        = string
  default     = null
}

variable "okta_url" {
  description = "(optional) - URL for Okta auth mode."
  type        = string
  default     = null
}

variable "okta_username_suffix" {
  description = "(optional) - Username suffix for Okta auth mode."
  type        = string
  default     = null
}

variable "otp_mode" {
  description = "(optional) - Two step authentication mode."
  type        = string
  default     = null
}

variable "peering_ha_eip" {
  description = "(optional) - Public IP address that you want assigned to the HA peering instance."
  type        = string
  default     = null
}

variable "peering_ha_gw_size" {
  description = "(optional) - Peering HA Gateway Size."
  type        = string
  default     = null
}

variable "peering_ha_insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Peering HA Gateway. Required if insane_mode is set."
  type        = string
  default     = null
}

variable "peering_ha_subnet" {
  description = "(optional) - Public Subnet Information while creating Peering HA Gateway, only subnet is accepted. Required to create peering ha gateway if cloud_type = 1 or 8 (AWS or AZURE). Optional if cloud_type = 4 (GCP)"
  type        = string
  default     = null
}

variable "peering_ha_zone" {
  description = "(optional) - Zone information for creating Peering HA Gateway. Required to create peering ha gateway if cloud_type = 4 (GCP). Optional for cloud_type = 8 (AZURE)."
  type        = string
  default     = null
}

variable "public_subnet_filtering_guard_duty_enforced" {
  description = "(optional) - Whether to enforce Guard Duty IP blocking. Required when `enable_public_subnet_filtering` attribute is true. Valid values: true or false. Default value: true."
  type        = bool
  default     = null
}

variable "public_subnet_filtering_ha_route_tables" {
  description = "(optional) - Route tables whose associated public subnets are protected for the HA PSF gateway. Required when enable_public_subnet_filtering and peering_ha_subnet are set."
  type        = set(string)
  default     = null
}

variable "public_subnet_filtering_route_tables" {
  description = "(optional) - Route tables whose associated public subnets are protected. Required when `enable_public_subnet_filtering` attribute is true."
  type        = set(string)
  default     = null
}

variable "renegotiation_interval" {
  description = "(optional) - Typed value when modifying renegotiation_interval. If it's -1, this feature is disabled."
  type        = number
  default     = null
}

variable "saml_enabled" {
  description = "(optional) - This field indicates whether to enable SAML or not."
  type        = bool
  default     = null
}

variable "search_domains" {
  description = "(optional) - A list of domain names that will use the NameServer when a specific name is not in the destination when Split Tunnel Mode is enabled."
  type        = string
  default     = null
}

variable "single_az_ha" {
  description = "(optional) - Set to true if this feature is desired."
  type        = bool
  default     = null
}

variable "single_ip_snat" {
  description = "(optional) - Enable Source NAT for this container."
  type        = bool
  default     = null
}

variable "split_tunnel" {
  description = "(optional) - Specify split tunnel mode."
  type        = bool
  default     = null
}

variable "subnet" {
  description = "(required) - A VPC Network address range selected from one of the available network ranges."
  type        = string
}

variable "tag_list" {
  description = "(optional) - Instance tag of cloud provider."
  type        = list(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of legacy VPC/Vnet to be connected."
  type        = string
}

variable "vpc_reg" {
  description = "(required) - Region where this gateway will be launched."
  type        = string
}

variable "vpn_access" {
  description = "(optional) - Enable user access through VPN to this container."
  type        = bool
  default     = null
}

variable "vpn_cidr" {
  description = "(optional) - VPN CIDR block for the container."
  type        = string
  default     = null
}

variable "vpn_protocol" {
  description = "(optional) - Elb protocol for VPN gateway with elb enabled. Only supports AWS provider. Valid values: 'TCP', 'UDP'. If not specified, 'TCP'' will be used."
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - Availability Zone. Only available for Azure and Public Subnet Filtering gateway"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_gateway" "this" {
  account_name                                = var.account_name
  additional_cidrs                            = var.additional_cidrs
  additional_cidrs_designated_gateway         = var.additional_cidrs_designated_gateway
  allocate_new_eip                            = var.allocate_new_eip
  cloud_type                                  = var.cloud_type
  customer_managed_keys                       = var.customer_managed_keys
  duo_api_hostname                            = var.duo_api_hostname
  duo_integration_key                         = var.duo_integration_key
  duo_push_mode                               = var.duo_push_mode
  duo_secret_key                              = var.duo_secret_key
  eip                                         = var.eip
  elb_name                                    = var.elb_name
  enable_designated_gateway                   = var.enable_designated_gateway
  enable_elb                                  = var.enable_elb
  enable_encrypt_volume                       = var.enable_encrypt_volume
  enable_jumbo_frame                          = var.enable_jumbo_frame
  enable_ldap                                 = var.enable_ldap
  enable_monitor_gateway_subnets              = var.enable_monitor_gateway_subnets
  enable_public_subnet_filtering              = var.enable_public_subnet_filtering
  enable_vpc_dns_server                       = var.enable_vpc_dns_server
  enable_vpn_nat                              = var.enable_vpn_nat
  fqdn_lan_cidr                               = var.fqdn_lan_cidr
  fqdn_lan_vpc_id                             = var.fqdn_lan_vpc_id
  gw_name                                     = var.gw_name
  gw_size                                     = var.gw_size
  idle_timeout                                = var.idle_timeout
  insane_mode                                 = var.insane_mode
  insane_mode_az                              = var.insane_mode_az
  ldap_base_dn                                = var.ldap_base_dn
  ldap_bind_dn                                = var.ldap_bind_dn
  ldap_password                               = var.ldap_password
  ldap_server                                 = var.ldap_server
  ldap_username_attribute                     = var.ldap_username_attribute
  max_vpn_conn                                = var.max_vpn_conn
  monitor_exclude_list                        = var.monitor_exclude_list
  name_servers                                = var.name_servers
  okta_token                                  = var.okta_token
  okta_url                                    = var.okta_url
  okta_username_suffix                        = var.okta_username_suffix
  otp_mode                                    = var.otp_mode
  peering_ha_eip                              = var.peering_ha_eip
  peering_ha_gw_size                          = var.peering_ha_gw_size
  peering_ha_insane_mode_az                   = var.peering_ha_insane_mode_az
  peering_ha_subnet                           = var.peering_ha_subnet
  peering_ha_zone                             = var.peering_ha_zone
  public_subnet_filtering_guard_duty_enforced = var.public_subnet_filtering_guard_duty_enforced
  public_subnet_filtering_ha_route_tables     = var.public_subnet_filtering_ha_route_tables
  public_subnet_filtering_route_tables        = var.public_subnet_filtering_route_tables
  renegotiation_interval                      = var.renegotiation_interval
  saml_enabled                                = var.saml_enabled
  search_domains                              = var.search_domains
  single_az_ha                                = var.single_az_ha
  single_ip_snat                              = var.single_ip_snat
  split_tunnel                                = var.split_tunnel
  subnet                                      = var.subnet
  tag_list                                    = var.tag_list
  vpc_id                                      = var.vpc_id
  vpc_reg                                     = var.vpc_reg
  vpn_access                                  = var.vpn_access
  vpn_cidr                                    = var.vpn_cidr
  vpn_protocol                                = var.vpn_protocol
  zone                                        = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_gateway.this.cloud_instance_id
}

output "eip" {
  description = "returns a string"
  value       = aviatrix_gateway.this.eip
}

output "elb_dns_name" {
  description = "returns a string"
  value       = aviatrix_gateway.this.elb_dns_name
}

output "elb_name" {
  description = "returns a string"
  value       = aviatrix_gateway.this.elb_name
}

output "fqdn_lan_interface" {
  description = "returns a string"
  value       = aviatrix_gateway.this.fqdn_lan_interface
}

output "id" {
  description = "returns a string"
  value       = aviatrix_gateway.this.id
}

output "peering_ha_cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_gateway.this.peering_ha_cloud_instance_id
}

output "peering_ha_eip" {
  description = "returns a string"
  value       = aviatrix_gateway.this.peering_ha_eip
}

output "peering_ha_gw_name" {
  description = "returns a string"
  value       = aviatrix_gateway.this.peering_ha_gw_name
}

output "peering_ha_private_ip" {
  description = "returns a string"
  value       = aviatrix_gateway.this.peering_ha_private_ip
}

output "private_ip" {
  description = "returns a string"
  value       = aviatrix_gateway.this.private_ip
}

output "public_dns_server" {
  description = "returns a string"
  value       = aviatrix_gateway.this.public_dns_server
}

output "security_group_id" {
  description = "returns a string"
  value       = aviatrix_gateway.this.security_group_id
}

output "vpn_protocol" {
  description = "returns a string"
  value       = aviatrix_gateway.this.vpn_protocol
}

output "this" {
  value = aviatrix_gateway.this
}
```

[top](#index)