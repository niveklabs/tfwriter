# aviatrix_aws_tgw_vpn_conn

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
module "aviatrix_aws_tgw_vpn_conn" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_vpn_conn"

  # connection_name - (required) is a type of string
  connection_name = null
  # connection_type - (optional) is a type of string
  connection_type = null
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = null
  # inside_ip_cidr_tun_1 - (optional) is a type of string
  inside_ip_cidr_tun_1 = null
  # inside_ip_cidr_tun_2 - (optional) is a type of string
  inside_ip_cidr_tun_2 = null
  # pre_shared_key_tun_1 - (optional) is a type of string
  pre_shared_key_tun_1 = null
  # pre_shared_key_tun_2 - (optional) is a type of string
  pre_shared_key_tun_2 = null
  # public_ip - (required) is a type of string
  public_ip = null
  # remote_as_number - (optional) is a type of string
  remote_as_number = null
  # remote_cidr - (optional) is a type of string
  remote_cidr = null
  # route_domain_name - (required) is a type of string
  route_domain_name = null
  # tgw_name - (required) is a type of string
  tgw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_name" {
  description = "(required) - Unique name of the connection."
  type        = string
}

variable "connection_type" {
  description = "(optional) - Connection type. Valid values: 'dynamic', 'static'. 'dynamic' stands for a BGP VPN connection; 'static' stands for a static VPN connection. Default value: 'dynamic'."
  type        = string
  default     = null
}

variable "enable_learned_cidrs_approval" {
  description = "(optional) - Switch to enable/disable encrypted transit approval for vpn connection. Valid values: true, false."
  type        = bool
  default     = null
}

variable "inside_ip_cidr_tun_1" {
  description = "(optional) - Inside IP CIDR for Tunnel 1. A /30 CIDR in 169.254.0.0/16."
  type        = string
  default     = null
}

variable "inside_ip_cidr_tun_2" {
  description = "(optional) - Inside IP CIDR for Tunnel 2. A /30 CIDR in 169.254.0.0/16."
  type        = string
  default     = null
}

variable "pre_shared_key_tun_1" {
  description = "(optional) - Pre-Shared Key for Tunnel 1. A 8-64 character string with alphanumeric, underscore(_) and dot(.). It cannot start with 0"
  type        = string
  default     = null
}

variable "pre_shared_key_tun_2" {
  description = "(optional) - Pre-Shared Key for Tunnel 2. A 8-64 character string with alphanumeric, underscore(_) and dot(.). It cannot start with 0"
  type        = string
  default     = null
}

variable "public_ip" {
  description = "(required) - Public IP address. Example: '40.0.0.0'."
  type        = string
}

variable "remote_as_number" {
  description = "(optional) - AWS side as a number. Integer between 1-4294967294. Example: '12'. Required for a dynamic VPN connection."
  type        = string
  default     = null
}

variable "remote_cidr" {
  description = "(optional) - Remote CIDRs joined as a string with ','. Required for a static VPN connection."
  type        = string
  default     = null
}

variable "route_domain_name" {
  description = "(required) - The name of a route domain, to which the vpn will be attached."
  type        = string
}

variable "tgw_name" {
  description = "(required) - This parameter represents the name of an AWS TGW."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_vpn_conn" "this" {
  connection_name               = var.connection_name
  connection_type               = var.connection_type
  enable_learned_cidrs_approval = var.enable_learned_cidrs_approval
  inside_ip_cidr_tun_1          = var.inside_ip_cidr_tun_1
  inside_ip_cidr_tun_2          = var.inside_ip_cidr_tun_2
  pre_shared_key_tun_1          = var.pre_shared_key_tun_1
  pre_shared_key_tun_2          = var.pre_shared_key_tun_2
  public_ip                     = var.public_ip
  remote_as_number              = var.remote_as_number
  remote_cidr                   = var.remote_cidr
  route_domain_name             = var.route_domain_name
  tgw_name                      = var.tgw_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_vpn_conn.this.id
}

output "vpn_id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_vpn_conn.this.vpn_id
}

output "this" {
  value = aviatrix_aws_tgw_vpn_conn.this
}
```

[top](#index)