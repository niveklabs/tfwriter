# aws_route
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_route" {
  source = "./modules/aws/r/aws_route"

  # destination_cidr_block - (optional) is a type of string
  destination_cidr_block = null
  # destination_ipv6_cidr_block - (optional) is a type of string
  destination_ipv6_cidr_block = null
  # egress_only_gateway_id - (optional) is a type of string
  egress_only_gateway_id = null
  # gateway_id - (optional) is a type of string
  gateway_id = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # local_gateway_id - (optional) is a type of string
  local_gateway_id = null
  # nat_gateway_id - (optional) is a type of string
  nat_gateway_id = null
  # network_interface_id - (optional) is a type of string
  network_interface_id = null
  # route_table_id - (required) is a type of string
  route_table_id = null
  # transit_gateway_id - (optional) is a type of string
  transit_gateway_id = null
  # vpc_endpoint_id - (optional) is a type of string
  vpc_endpoint_id = null
  # vpc_peering_connection_id - (optional) is a type of string
  vpc_peering_connection_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "destination_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_ipv6_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "egress_only_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_interface_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "transit_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_peering_connection_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_route" "this" {
  destination_cidr_block      = var.destination_cidr_block
  destination_ipv6_cidr_block = var.destination_ipv6_cidr_block
  egress_only_gateway_id      = var.egress_only_gateway_id
  gateway_id                  = var.gateway_id
  instance_id                 = var.instance_id
  local_gateway_id            = var.local_gateway_id
  nat_gateway_id              = var.nat_gateway_id
  network_interface_id        = var.network_interface_id
  route_table_id              = var.route_table_id
  transit_gateway_id          = var.transit_gateway_id
  vpc_endpoint_id             = var.vpc_endpoint_id
  vpc_peering_connection_id   = var.vpc_peering_connection_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "destination_prefix_list_id" {
  description = "returns a string"
  value       = aws_route.this.destination_prefix_list_id
}

output "egress_only_gateway_id" {
  description = "returns a string"
  value       = aws_route.this.egress_only_gateway_id
}

output "gateway_id" {
  description = "returns a string"
  value       = aws_route.this.gateway_id
}

output "id" {
  description = "returns a string"
  value       = aws_route.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = aws_route.this.instance_id
}

output "instance_owner_id" {
  description = "returns a string"
  value       = aws_route.this.instance_owner_id
}

output "local_gateway_id" {
  description = "returns a string"
  value       = aws_route.this.local_gateway_id
}

output "nat_gateway_id" {
  description = "returns a string"
  value       = aws_route.this.nat_gateway_id
}

output "network_interface_id" {
  description = "returns a string"
  value       = aws_route.this.network_interface_id
}

output "origin" {
  description = "returns a string"
  value       = aws_route.this.origin
}

output "state" {
  description = "returns a string"
  value       = aws_route.this.state
}

output "this" {
  value = aws_route.this
}
```
[top](#index)
