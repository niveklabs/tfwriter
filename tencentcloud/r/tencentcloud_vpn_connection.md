# tencentcloud_vpn_connection

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_vpn_connection" {
  source = "./modules/tencentcloud/r/tencentcloud_vpn_connection"

  # customer_gateway_id - (required) is a type of string
  customer_gateway_id = null
  # ike_dh_group_name - (optional) is a type of string
  ike_dh_group_name = null
  # ike_exchange_mode - (optional) is a type of string
  ike_exchange_mode = null
  # ike_local_address - (optional) is a type of string
  ike_local_address = null
  # ike_local_fqdn_name - (optional) is a type of string
  ike_local_fqdn_name = null
  # ike_local_identity - (optional) is a type of string
  ike_local_identity = null
  # ike_proto_authen_algorithm - (optional) is a type of string
  ike_proto_authen_algorithm = null
  # ike_proto_encry_algorithm - (optional) is a type of string
  ike_proto_encry_algorithm = null
  # ike_remote_address - (optional) is a type of string
  ike_remote_address = null
  # ike_remote_fqdn_name - (optional) is a type of string
  ike_remote_fqdn_name = null
  # ike_remote_identity - (optional) is a type of string
  ike_remote_identity = null
  # ike_sa_lifetime_seconds - (optional) is a type of number
  ike_sa_lifetime_seconds = null
  # ike_version - (optional) is a type of string
  ike_version = null
  # ipsec_encrypt_algorithm - (optional) is a type of string
  ipsec_encrypt_algorithm = null
  # ipsec_integrity_algorithm - (optional) is a type of string
  ipsec_integrity_algorithm = null
  # ipsec_pfs_dh_group - (optional) is a type of string
  ipsec_pfs_dh_group = null
  # ipsec_sa_lifetime_seconds - (optional) is a type of number
  ipsec_sa_lifetime_seconds = null
  # ipsec_sa_lifetime_traffic - (optional) is a type of number
  ipsec_sa_lifetime_traffic = null
  # name - (required) is a type of string
  name = null
  # pre_share_key - (required) is a type of string
  pre_share_key = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null

  security_group_policy = [{
    local_cidr_block  = null
    remote_cidr_block = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "customer_gateway_id" {
  description = "(required) - ID of the customer gateway."
  type        = string
}

variable "ike_dh_group_name" {
  description = "(optional) - DH group name of the IKE operation specification. Valid values: `GROUP1`, `GROUP2`, `GROUP5`, `GROUP14`, `GROUP24`. Default value is `GROUP1`."
  type        = string
  default     = null
}

variable "ike_exchange_mode" {
  description = "(optional) - Exchange mode of the IKE operation specification. Valid values: `AGGRESSIVE`, `MAIN`. Default value is `MAIN`."
  type        = string
  default     = null
}

variable "ike_local_address" {
  description = "(optional) - Local address of IKE operation specification, valid when ike_local_identity is `ADDRESS`, generally the value is `public_ip_address` of the related VPN gateway."
  type        = string
  default     = null
}

variable "ike_local_fqdn_name" {
  description = "(optional) - Local FQDN name of the IKE operation specification."
  type        = string
  default     = null
}

variable "ike_local_identity" {
  description = "(optional) - Local identity way of IKE operation specification. Valid values: `ADDRESS`, `FQDN`. Default value is `ADDRESS`."
  type        = string
  default     = null
}

variable "ike_proto_authen_algorithm" {
  description = "(optional) - Proto authenticate algorithm of the IKE operation specification. Valid values: `MD5`, `SHA`. Default Value is `MD5`."
  type        = string
  default     = null
}

variable "ike_proto_encry_algorithm" {
  description = "(optional) - Proto encrypt algorithm of the IKE operation specification. Valid values: `3DES-CBC`, `AES-CBC-128`, `AES-CBC-128`, `AES-CBC-256`, `DES-CBC`. Default value is `3DES-CBC`."
  type        = string
  default     = null
}

variable "ike_remote_address" {
  description = "(optional) - Remote address of IKE operation specification, valid when ike_remote_identity is `ADDRESS`, generally the value is `public_ip_address` of the related customer gateway."
  type        = string
  default     = null
}

variable "ike_remote_fqdn_name" {
  description = "(optional) - Remote FQDN name of the IKE operation specification."
  type        = string
  default     = null
}

variable "ike_remote_identity" {
  description = "(optional) - Remote identity way of IKE operation specification. Valid values: `ADDRESS`, `FQDN`. Default value is `ADDRESS`."
  type        = string
  default     = null
}

variable "ike_sa_lifetime_seconds" {
  description = "(optional) - SA lifetime of the IKE operation specification, unit is `second`. The value ranges from 60 to 604800. Default value is 86400 seconds."
  type        = number
  default     = null
}

variable "ike_version" {
  description = "(optional) - Version of the IKE operation specification. Default value is `IKEV1`."
  type        = string
  default     = null
}

variable "ipsec_encrypt_algorithm" {
  description = "(optional) - Encrypt algorithm of the IPSEC operation specification. Valid values: `3DES-CBC`, `AES-CBC-128`, `AES-CBC-128`, `AES-CBC-256`, `DES-CBC`. Default value is `3DES-CBC`."
  type        = string
  default     = null
}

variable "ipsec_integrity_algorithm" {
  description = "(optional) - Integrity algorithm of the IPSEC operation specification. Valid values: `SHA1`, `MD5`. Default value is `MD5`."
  type        = string
  default     = null
}

variable "ipsec_pfs_dh_group" {
  description = "(optional) - PFS DH group. Valid value: `GROUP1`, `GROUP2`, `GROUP5`, `GROUP14`, `GROUP24`, `NULL`. Default value is `NULL`."
  type        = string
  default     = null
}

variable "ipsec_sa_lifetime_seconds" {
  description = "(optional) - SA lifetime of the IPSEC operation specification, unit is second. Valid value ranges: [180~604800]. Default value is 3600 seconds."
  type        = number
  default     = null
}

variable "ipsec_sa_lifetime_traffic" {
  description = "(optional) - SA lifetime of the IPSEC operation specification, unit is KB. The value should not be less then 2560. Default value is 1843200."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the VPN connection. The length of character is limited to 1-60."
  type        = string
}

variable "pre_share_key" {
  description = "(required) - Pre-shared key of the VPN connection."
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tags used to associate different resources."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC. Required if vpn gateway is not in `CCN` type, and doesn't make sense for `CCN` vpn gateway."
  type        = string
  default     = null
}

variable "vpn_gateway_id" {
  description = "(required) - ID of the VPN gateway."
  type        = string
}

variable "security_group_policy" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      local_cidr_block  = string
      remote_cidr_block = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vpn_connection" "this" {
  customer_gateway_id        = var.customer_gateway_id
  ike_dh_group_name          = var.ike_dh_group_name
  ike_exchange_mode          = var.ike_exchange_mode
  ike_local_address          = var.ike_local_address
  ike_local_fqdn_name        = var.ike_local_fqdn_name
  ike_local_identity         = var.ike_local_identity
  ike_proto_authen_algorithm = var.ike_proto_authen_algorithm
  ike_proto_encry_algorithm  = var.ike_proto_encry_algorithm
  ike_remote_address         = var.ike_remote_address
  ike_remote_fqdn_name       = var.ike_remote_fqdn_name
  ike_remote_identity        = var.ike_remote_identity
  ike_sa_lifetime_seconds    = var.ike_sa_lifetime_seconds
  ike_version                = var.ike_version
  ipsec_encrypt_algorithm    = var.ipsec_encrypt_algorithm
  ipsec_integrity_algorithm  = var.ipsec_integrity_algorithm
  ipsec_pfs_dh_group         = var.ipsec_pfs_dh_group
  ipsec_sa_lifetime_seconds  = var.ipsec_sa_lifetime_seconds
  ipsec_sa_lifetime_traffic  = var.ipsec_sa_lifetime_traffic
  name                       = var.name
  pre_share_key              = var.pre_share_key
  tags                       = var.tags
  vpc_id                     = var.vpc_id
  vpn_gateway_id             = var.vpn_gateway_id

  dynamic "security_group_policy" {
    for_each = var.security_group_policy
    content {
      local_cidr_block  = security_group_policy.value["local_cidr_block"]
      remote_cidr_block = security_group_policy.value["remote_cidr_block"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.create_time
}

output "encrypt_proto" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.encrypt_proto
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.id
}

output "is_ccn_type" {
  description = "returns a bool"
  value       = tencentcloud_vpn_connection.this.is_ccn_type
}

output "net_status" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.net_status
}

output "route_type" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.route_type
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.state
}

output "vpn_proto" {
  description = "returns a string"
  value       = tencentcloud_vpn_connection.this.vpn_proto
}

output "this" {
  value = tencentcloud_vpn_connection.this
}
```

[top](#index)