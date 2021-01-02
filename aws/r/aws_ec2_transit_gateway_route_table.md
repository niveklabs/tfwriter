# aws_ec2_transit_gateway_route_table

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_transit_gateway_route_table" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_route_table"

  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_id - (required) is a type of string
  transit_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transit_gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_transit_gateway_route_table" "this" {
  tags               = var.tags
  transit_gateway_id = var.transit_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_route_table.this.arn
}

output "default_association_route_table" {
  description = "returns a bool"
  value       = aws_ec2_transit_gateway_route_table.this.default_association_route_table
}

output "default_propagation_route_table" {
  description = "returns a bool"
  value       = aws_ec2_transit_gateway_route_table.this.default_propagation_route_table
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_route_table.this.id
}

output "this" {
  value = aws_ec2_transit_gateway_route_table.this
}
```

[top](#index)