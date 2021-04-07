# aviatrix_transit_gateway

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
module "aviatrix_transit_gateway" {
  source = "./modules/aviatrix/d/aviatrix_transit_gateway"

  # gw_name - (required) is a type of string
  gw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "gw_name" {
  description = "(required) - Transit Gateway name. This can be used for getting gateway."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_transit_gateway" "this" {
  # gw_name - (required) is a type of string
  gw_name = var.gw_name
}
```

[top](#index)

### Outputs

```terraform
output "account_name" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.account_name
}

output "allocate_new_eip" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.allocate_new_eip
}

output "bgp_manual_spoke_advertise_cidrs" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.bgp_manual_spoke_advertise_cidrs
}

output "cloud_instance_id" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.cloud_instance_id
}

output "cloud_type" {
  description = "returns a number"
  value       = data.aviatrix_transit_gateway.this.cloud_type
}

output "connected_transit" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.connected_transit
}

output "customized_spoke_vpc_routes" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.customized_spoke_vpc_routes
}

output "customized_transit_vpc_routes" {
  description = "returns a set of string"
  value       = data.aviatrix_transit_gateway.this.customized_transit_vpc_routes
}

output "enable_active_mesh" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_active_mesh
}

output "enable_advertise_transit_cidr" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_advertise_transit_cidr
}

output "enable_egress_transit_firenet" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_egress_transit_firenet
}

output "enable_encrypt_volume" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_encrypt_volume
}

output "enable_firenet" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_firenet
}

output "enable_hybrid_connection" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_hybrid_connection
}

output "enable_learned_cidrs_approval" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_learned_cidrs_approval
}

output "enable_private_oob" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_private_oob
}

output "enable_transit_firenet" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_transit_firenet
}

output "enable_vpc_dns_server" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.enable_vpc_dns_server
}

output "excluded_advertised_spoke_routes" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.excluded_advertised_spoke_routes
}

output "filtered_spoke_vpc_routes" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.filtered_spoke_vpc_routes
}

output "gw_size" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.gw_size
}

output "ha_cloud_instance_id" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_cloud_instance_id
}

output "ha_gw_name" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_gw_name
}

output "ha_gw_size" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_gw_size
}

output "ha_insane_mode_az" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_insane_mode_az
}

output "ha_oob_availability_zone" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_oob_availability_zone
}

output "ha_oob_management_subnet" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_oob_management_subnet
}

output "ha_private_ip" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_private_ip
}

output "ha_public_ip" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_public_ip
}

output "ha_subnet" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_subnet
}

output "ha_zone" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.ha_zone
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.id
}

output "insane_mode" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.insane_mode
}

output "insane_mode_az" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.insane_mode_az
}

output "oob_availability_zone" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.oob_availability_zone
}

output "oob_management_subnet" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.oob_management_subnet
}

output "private_ip" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.private_ip
}

output "public_ip" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.public_ip
}

output "security_group_id" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.security_group_id
}

output "single_az_ha" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.single_az_ha
}

output "single_ip_snat" {
  description = "returns a bool"
  value       = data.aviatrix_transit_gateway.this.single_ip_snat
}

output "subnet" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.subnet
}

output "tag_list" {
  description = "returns a list of string"
  value       = data.aviatrix_transit_gateway.this.tag_list
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.vpc_id
}

output "vpc_reg" {
  description = "returns a string"
  value       = data.aviatrix_transit_gateway.this.vpc_reg
}

output "this" {
  value = aviatrix_transit_gateway.this
}
```

[top](#index)