# aws_route_table

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
module "aws_route_table" {
  source = "./modules/aws/r/aws_route_table"

  # propagating_vgws - (optional) is a type of set of string
  propagating_vgws = []
  # route - (optional) is a type of set of object
  route = [{
    cidr_block                = null
    egress_only_gateway_id    = null
    gateway_id                = null
    instance_id               = null
    ipv6_cidr_block           = null
    local_gateway_id          = null
    nat_gateway_id            = null
    network_interface_id      = null
    transit_gateway_id        = null
    vpc_endpoint_id           = null
    vpc_peering_connection_id = null
  }]
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```hcl
variable "propagating_vgws" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "route" {
  description = "(optional)"
  type = set(object(
    {
      cidr_block                = string
      egress_only_gateway_id    = string
      gateway_id                = string
      instance_id               = string
      ipv6_cidr_block           = string
      local_gateway_id          = string
      nat_gateway_id            = string
      network_interface_id      = string
      transit_gateway_id        = string
      vpc_endpoint_id           = string
      vpc_peering_connection_id = string
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_route_table" "this" {
  propagating_vgws = var.propagating_vgws
  route            = var.route
  tags             = var.tags
  vpc_id           = var.vpc_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_route_table.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_route_table.this.owner_id
}

output "propagating_vgws" {
  description = "returns a set of string"
  value       = aws_route_table.this.propagating_vgws
}

output "route" {
  description = "returns a set of object"
  value       = aws_route_table.this.route
}

output "this" {
  value = aws_route_table.this
}
```

[top](#index)