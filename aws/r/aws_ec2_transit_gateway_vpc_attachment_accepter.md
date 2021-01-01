# aws_ec2_transit_gateway_vpc_attachment_accepter

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
module "aws_ec2_transit_gateway_vpc_attachment_accepter" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_vpc_attachment_accepter"

  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_attachment_id - (required) is a type of string
  transit_gateway_attachment_id = null
  # transit_gateway_default_route_table_association - (optional) is a type of bool
  transit_gateway_default_route_table_association = null
  # transit_gateway_default_route_table_propagation - (optional) is a type of bool
  transit_gateway_default_route_table_propagation = null
}
```

[top](#index)

### Variables

```hcl
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transit_gateway_attachment_id" {
  description = "(required)"
  type        = string
}

variable "transit_gateway_default_route_table_association" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "transit_gateway_default_route_table_propagation" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_ec2_transit_gateway_vpc_attachment_accepter" "this" {
  tags                                            = var.tags
  transit_gateway_attachment_id                   = var.transit_gateway_attachment_id
  transit_gateway_default_route_table_association = var.transit_gateway_default_route_table_association
  transit_gateway_default_route_table_propagation = var.transit_gateway_default_route_table_propagation
}
```

[top](#index)

### Outputs

```hcl
output "appliance_mode_support" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.appliance_mode_support
}

output "dns_support" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.dns_support
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.id
}

output "ipv6_support" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.ipv6_support
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.subnet_ids
}

output "transit_gateway_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.transit_gateway_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.vpc_id
}

output "vpc_owner_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment_accepter.this.vpc_owner_id
}

output "this" {
  value = aws_ec2_transit_gateway_vpc_attachment_accepter.this
}
```

[top](#index)