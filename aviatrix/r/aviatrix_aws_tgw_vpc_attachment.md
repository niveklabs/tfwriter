# aviatrix_aws_tgw_vpc_attachment

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
module "aviatrix_aws_tgw_vpc_attachment" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_vpc_attachment"

  # customized_route_advertisement - (optional) is a type of string
  customized_route_advertisement = null
  # customized_routes - (optional) is a type of string
  customized_routes = null
  # disable_local_route_propagation - (optional) is a type of bool
  disable_local_route_propagation = null
  # edge_attachment - (optional) is a type of string
  edge_attachment = null
  # region - (required) is a type of string
  region = null
  # route_tables - (optional) is a type of string
  route_tables = null
  # security_domain_name - (required) is a type of string
  security_domain_name = null
  # subnets - (optional) is a type of string
  subnets = null
  # tgw_name - (required) is a type of string
  tgw_name = null
  # vpc_account_name - (required) is a type of string
  vpc_account_name = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "customized_route_advertisement" {
  description = "(optional) - Advanced option. Customized route(s) to be advertised to other VPCs that are connected to the same TGW."
  type        = string
  default     = null
}

variable "customized_routes" {
  description = "(optional) - Advanced option. Customized Spoke VPC Routes. It allows the admin to enter non-RFC1918 routes in the VPC route table targeting the TGW."
  type        = string
  default     = null
}

variable "disable_local_route_propagation" {
  description = "(optional) - Advanced option. If set to true, it disables automatic route propagation of this VPC to other VPCs within the same security domain."
  type        = bool
  default     = null
}

variable "edge_attachment" {
  description = "(optional) - Edge attachment ID. To allow access to the private IP of the MGMT interface of the Firewalls, set this attribute to enable Management Access From Onprem. This feature advertises the Firewalls private MGMT subnet to your Edge domain."
  type        = string
  default     = null
}

variable "region" {
  description = "(required) - Region of cloud provider."
  type        = string
}

variable "route_tables" {
  description = "(optional) - Advanced option. Route tables separated by ',' to participate in TGW Orchestrator, i.e., learned routes will be propagated to these route tables."
  type        = string
  default     = null
}

variable "security_domain_name" {
  description = "(required) - The name of the security domain."
  type        = string
}

variable "subnets" {
  description = "(optional) - Advanced option. VPC subnets separated by ',' to attach to the VPC. If left blank, Aviatrix Controller automatically selects a subnet representing each AZ for the VPC attachment."
  type        = string
  default     = null
}

variable "tgw_name" {
  description = "(required) - Name of the AWS TGW."
  type        = string
}

variable "vpc_account_name" {
  description = "(required) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
}

variable "vpc_id" {
  description = "(required) - This parameter represents the ID of the VPC."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_vpc_attachment" "this" {
  customized_route_advertisement  = var.customized_route_advertisement
  customized_routes               = var.customized_routes
  disable_local_route_propagation = var.disable_local_route_propagation
  edge_attachment                 = var.edge_attachment
  region                          = var.region
  route_tables                    = var.route_tables
  security_domain_name            = var.security_domain_name
  subnets                         = var.subnets
  tgw_name                        = var.tgw_name
  vpc_account_name                = var.vpc_account_name
  vpc_id                          = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_vpc_attachment.this.id
}

output "route_tables" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_vpc_attachment.this.route_tables
}

output "subnets" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_vpc_attachment.this.subnets
}

output "this" {
  value = aviatrix_aws_tgw_vpc_attachment.this
}
```

[top](#index)