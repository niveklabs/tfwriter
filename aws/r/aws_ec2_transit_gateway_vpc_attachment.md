# aws_ec2_transit_gateway_vpc_attachment

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ec2_transit_gateway_vpc_attachment" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_vpc_attachment"

  # appliance_mode_support - (optional) is a type of string
  appliance_mode_support = null
  # dns_support - (optional) is a type of string
  dns_support = null
  # ipv6_support - (optional) is a type of string
  ipv6_support = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_default_route_table_association - (optional) is a type of bool
  transit_gateway_default_route_table_association = null
  # transit_gateway_default_route_table_propagation - (optional) is a type of bool
  transit_gateway_default_route_table_propagation = null
  # transit_gateway_id - (required) is a type of string
  transit_gateway_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```hcl
variable "appliance_mode_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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

variable "transit_gateway_id" {
  description = "(required)"
  type        = string
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ec2_transit_gateway_vpc_attachment" "this" {
  appliance_mode_support                          = var.appliance_mode_support
  dns_support                                     = var.dns_support
  ipv6_support                                    = var.ipv6_support
  subnet_ids                                      = var.subnet_ids
  tags                                            = var.tags
  transit_gateway_default_route_table_association = var.transit_gateway_default_route_table_association
  transit_gateway_default_route_table_propagation = var.transit_gateway_default_route_table_propagation
  transit_gateway_id                              = var.transit_gateway_id
  vpc_id                                          = var.vpc_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment.this.id
}

output "vpc_owner_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_vpc_attachment.this.vpc_owner_id
}

output "this" {
  value = aws_ec2_transit_gateway_vpc_attachment.this
}
```

[top](#index)