# aviatrix_gateway

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aviatrix/d/aviatrix_gateway"

  # gw_name - (required) is a type of string
  gw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "gw_name" {
  description = "(required) - Gateway name. This can be used for getting gateway."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_gateway" "this" {
  gw_name = var.gw_name
}
```

[top](#index)

### Outputs

```terraform
output "account_name" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.account_name
}

output "additional_cidrs" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.additional_cidrs
}

output "additional_cidrs_designated_gateway" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.additional_cidrs_designated_gateway
}

output "allocate_new_eip" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.allocate_new_eip
}

output "cloud_instance_id" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.cloud_instance_id
}

output "cloud_type" {
  description = "returns a number"
  value       = data.aviatrix_gateway.this.cloud_type
}

output "duo_api_hostname" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.duo_api_hostname
}

output "duo_integration_key" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.duo_integration_key
}

output "duo_push_mode" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.duo_push_mode
}

output "elb_dns_name" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.elb_dns_name
}

output "elb_name" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.elb_name
}

output "enable_designated_gateway" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.enable_designated_gateway
}

output "enable_elb" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.enable_elb
}

output "enable_encrypt_volume" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.enable_encrypt_volume
}

output "enable_ldap" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.enable_ldap
}

output "enable_vpc_dns_server" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.enable_vpc_dns_server
}

output "enable_vpn_nat" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.enable_vpn_nat
}

output "gw_size" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.gw_size
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.id
}

output "insane_mode" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.insane_mode
}

output "insane_mode_az" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.insane_mode_az
}

output "ldap_base_dn" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.ldap_base_dn
}

output "ldap_bind_dn" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.ldap_bind_dn
}

output "ldap_server" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.ldap_server
}

output "ldap_username_attribute" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.ldap_username_attribute
}

output "max_vpn_conn" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.max_vpn_conn
}

output "name_servers" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.name_servers
}

output "okta_url" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.okta_url
}

output "okta_username_suffix" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.okta_username_suffix
}

output "otp_mode" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.otp_mode
}

output "peering_ha_cloud_instance_id" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_cloud_instance_id
}

output "peering_ha_gw_name" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_gw_name
}

output "peering_ha_gw_size" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_gw_size
}

output "peering_ha_insane_mode_az" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_insane_mode_az
}

output "peering_ha_private_ip" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_private_ip
}

output "peering_ha_public_ip" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_public_ip
}

output "peering_ha_subnet" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_subnet
}

output "peering_ha_zone" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.peering_ha_zone
}

output "private_ip" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.private_ip
}

output "public_dns_server" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.public_dns_server
}

output "public_ip" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.public_ip
}

output "saml_enabled" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.saml_enabled
}

output "search_domains" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.search_domains
}

output "security_group_id" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.security_group_id
}

output "single_az_ha" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.single_az_ha
}

output "single_ip_snat" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.single_ip_snat
}

output "split_tunnel" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.split_tunnel
}

output "subnet" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.subnet
}

output "tag_list" {
  description = "returns a list of string"
  value       = data.aviatrix_gateway.this.tag_list
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.vpc_id
}

output "vpc_reg" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.vpc_reg
}

output "vpn_access" {
  description = "returns a bool"
  value       = data.aviatrix_gateway.this.vpn_access
}

output "vpn_cidr" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.vpn_cidr
}

output "vpn_protocol" {
  description = "returns a string"
  value       = data.aviatrix_gateway.this.vpn_protocol
}

output "this" {
  value = aviatrix_gateway.this
}
```

[top](#index)