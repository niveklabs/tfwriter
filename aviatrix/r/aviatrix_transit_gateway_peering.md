# aviatrix_transit_gateway_peering

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
module "aviatrix_transit_gateway_peering" {
  source = "./modules/aviatrix/r/aviatrix_transit_gateway_peering"

  # enable_peering_over_private_network - (optional) is a type of bool
  enable_peering_over_private_network = null
  # enable_single_tunnel_mode - (optional) is a type of bool
  enable_single_tunnel_mode = null
  # gateway1_excluded_network_cidrs - (optional) is a type of list of string
  gateway1_excluded_network_cidrs = []
  # gateway1_excluded_tgw_connections - (optional) is a type of list of string
  gateway1_excluded_tgw_connections = []
  # gateway2_excluded_network_cidrs - (optional) is a type of list of string
  gateway2_excluded_network_cidrs = []
  # gateway2_excluded_tgw_connections - (optional) is a type of list of string
  gateway2_excluded_tgw_connections = []
  # prepend_as_path1 - (optional) is a type of set of string
  prepend_as_path1 = []
  # prepend_as_path2 - (optional) is a type of set of string
  prepend_as_path2 = []
  # transit_gateway_name1 - (required) is a type of string
  transit_gateway_name1 = null
  # transit_gateway_name2 - (required) is a type of string
  transit_gateway_name2 = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_peering_over_private_network" {
  description = "(optional) - (Optional) Enable peering over private network. Insane mode is required on both transit gateways. Available as of provider version R2.17.1"
  type        = bool
  default     = null
}

variable "enable_single_tunnel_mode" {
  description = "(optional) - Enable peering with Single-Tunnel mode."
  type        = bool
  default     = null
}

variable "gateway1_excluded_network_cidrs" {
  description = "(optional) - List of excluded network CIDRs for the first transit gateway."
  type        = list(string)
  default     = null
}

variable "gateway1_excluded_tgw_connections" {
  description = "(optional) - List of excluded TGW connections for the first transit gateway."
  type        = list(string)
  default     = null
}

variable "gateway2_excluded_network_cidrs" {
  description = "(optional) - List of excluded network CIDRs for the second transit gateway."
  type        = list(string)
  default     = null
}

variable "gateway2_excluded_tgw_connections" {
  description = "(optional) - List of excluded TGW connections for the second transit gateway."
  type        = list(string)
  default     = null
}

variable "prepend_as_path1" {
  description = "(optional) - AS Path Prepend customized by specifying AS PATH for a BGP connection. Applies on transit_gateway_name1."
  type        = set(string)
  default     = null
}

variable "prepend_as_path2" {
  description = "(optional) - AS Path Prepend customized by specifying AS PATH for a BGP connection. Applies on transit_gateway_name2."
  type        = set(string)
  default     = null
}

variable "transit_gateway_name1" {
  description = "(required) - The first transit gateway name to make a peer pair."
  type        = string
}

variable "transit_gateway_name2" {
  description = "(required) - The second transit gateway name to make a peer pair."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_transit_gateway_peering" "this" {
  enable_peering_over_private_network = var.enable_peering_over_private_network
  enable_single_tunnel_mode           = var.enable_single_tunnel_mode
  gateway1_excluded_network_cidrs     = var.gateway1_excluded_network_cidrs
  gateway1_excluded_tgw_connections   = var.gateway1_excluded_tgw_connections
  gateway2_excluded_network_cidrs     = var.gateway2_excluded_network_cidrs
  gateway2_excluded_tgw_connections   = var.gateway2_excluded_tgw_connections
  prepend_as_path1                    = var.prepend_as_path1
  prepend_as_path2                    = var.prepend_as_path2
  transit_gateway_name1               = var.transit_gateway_name1
  transit_gateway_name2               = var.transit_gateway_name2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_transit_gateway_peering.this.id
}

output "this" {
  value = aviatrix_transit_gateway_peering.this
}
```

[top](#index)