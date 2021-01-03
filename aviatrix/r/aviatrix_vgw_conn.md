# aviatrix_vgw_conn

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
module "aviatrix_vgw_conn" {
  source = "./modules/aviatrix/r/aviatrix_vgw_conn"

  # bgp_local_as_num - (required) is a type of string
  bgp_local_as_num = null
  # bgp_vgw_account - (required) is a type of string
  bgp_vgw_account = null
  # bgp_vgw_id - (required) is a type of string
  bgp_vgw_id = null
  # bgp_vgw_region - (required) is a type of string
  bgp_vgw_region = null
  # conn_name - (required) is a type of string
  conn_name = null
  # gw_name - (required) is a type of string
  gw_name = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bgp_local_as_num" {
  description = "(required) - BGP local ASN (Autonomous System Number). Integer between 1-4294967294."
  type        = string
}

variable "bgp_vgw_account" {
  description = "(required) - Account of AWS's VGW that is used for this connection."
  type        = string
}

variable "bgp_vgw_id" {
  description = "(required) - Id of AWS's VGW that is used for this connection."
  type        = string
}

variable "bgp_vgw_region" {
  description = "(required) - Region of AWS's VGW that is used for this connection."
  type        = string
}

variable "conn_name" {
  description = "(required) - The name of the VGW connection which is going to be created."
  type        = string
}

variable "gw_name" {
  description = "(required) - Name of the Transit Gateway."
  type        = string
}

variable "vpc_id" {
  description = "(required) - VPC-ID where the Transit Gateway is located."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_vgw_conn" "this" {
  bgp_local_as_num = var.bgp_local_as_num
  bgp_vgw_account  = var.bgp_vgw_account
  bgp_vgw_id       = var.bgp_vgw_id
  bgp_vgw_region   = var.bgp_vgw_region
  conn_name        = var.conn_name
  gw_name          = var.gw_name
  vpc_id           = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_vgw_conn.this.id
}

output "this" {
  value = aviatrix_vgw_conn.this
}
```

[top](#index)