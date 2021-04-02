# aws_default_route_table

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_default_route_table" {
  source = "./modules/aws/r/aws_default_route_table"

  # default_route_table_id - (required) is a type of string
  default_route_table_id = null
  # propagating_vgws - (optional) is a type of set of string
  propagating_vgws = []
  # route - (optional) is a type of set of object
  route = [{
    cidr_block                 = null
    destination_prefix_list_id = null
    egress_only_gateway_id     = null
    gateway_id                 = null
    instance_id                = null
    ipv6_cidr_block            = null
    nat_gateway_id             = null
    network_interface_id       = null
    transit_gateway_id         = null
    vpc_endpoint_id            = null
    vpc_peering_connection_id  = null
  }]
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "default_route_table_id" {
  description = "(required)"
  type        = string
}

variable "propagating_vgws" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "route" {
  description = "(optional)"
  type = set(object(
    {
      cidr_block                 = string
      destination_prefix_list_id = string
      egress_only_gateway_id     = string
      gateway_id                 = string
      instance_id                = string
      ipv6_cidr_block            = string
      nat_gateway_id             = string
      network_interface_id       = string
      transit_gateway_id         = string
      vpc_endpoint_id            = string
      vpc_peering_connection_id  = string
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_default_route_table" "this" {
  default_route_table_id = var.default_route_table_id
  propagating_vgws       = var.propagating_vgws
  route                  = var.route
  tags                   = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_default_route_table.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_default_route_table.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_default_route_table.this.owner_id
}

output "route" {
  description = "returns a set of object"
  value       = aws_default_route_table.this.route
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_default_route_table.this.vpc_id
}

output "this" {
  value = aws_default_route_table.this
}
```

[top](#index)