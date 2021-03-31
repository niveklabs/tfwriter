# aviatrix_aws_tgw_connect_peer

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
module "aviatrix_aws_tgw_connect_peer" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_connect_peer"

  # bgp_inside_cidrs - (required) is a type of set of string
  bgp_inside_cidrs = []
  # connect_attachment_id - (required) is a type of string
  connect_attachment_id = null
  # connect_peer_name - (required) is a type of string
  connect_peer_name = null
  # connection_name - (required) is a type of string
  connection_name = null
  # peer_as_number - (required) is a type of string
  peer_as_number = null
  # peer_gre_address - (required) is a type of string
  peer_gre_address = null
  # tgw_gre_address - (optional) is a type of string
  tgw_gre_address = null
  # tgw_name - (required) is a type of string
  tgw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "bgp_inside_cidrs" {
  description = "(required) - Set of BGP Inside CIDR Blocks."
  type        = set(string)
}

variable "connect_attachment_id" {
  description = "(required) - Connect Attachment ID."
  type        = string
}

variable "connect_peer_name" {
  description = "(required) - Connect Peer Name."
  type        = string
}

variable "connection_name" {
  description = "(required) - AWS TGW Connect connection name."
  type        = string
}

variable "peer_as_number" {
  description = "(required) - Peer AS Number."
  type        = string
}

variable "peer_gre_address" {
  description = "(required) - Peer GRE IP Address."
  type        = string
}

variable "tgw_gre_address" {
  description = "(optional) - AWS TGW GRE IP Address."
  type        = string
  default     = null
}

variable "tgw_name" {
  description = "(required) - AWS TGW Name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_connect_peer" "this" {
  bgp_inside_cidrs      = var.bgp_inside_cidrs
  connect_attachment_id = var.connect_attachment_id
  connect_peer_name     = var.connect_peer_name
  connection_name       = var.connection_name
  peer_as_number        = var.peer_as_number
  peer_gre_address      = var.peer_gre_address
  tgw_gre_address       = var.tgw_gre_address
  tgw_name              = var.tgw_name
}
```

[top](#index)

### Outputs

```terraform
output "connect_peer_id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_connect_peer.this.connect_peer_id
}

output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_connect_peer.this.id
}

output "this" {
  value = aviatrix_aws_tgw_connect_peer.this
}
```

[top](#index)