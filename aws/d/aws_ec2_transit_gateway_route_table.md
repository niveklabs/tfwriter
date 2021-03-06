# aws_ec2_transit_gateway_route_table

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ec2_transit_gateway_route_table" {
  source = "./modules/aws/d/aws_ec2_transit_gateway_route_table"

  # tags - (optional) is a type of map of string
  tags = {}

  filter = [{
    name   = null
    values = []
  }]
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

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_ec2_transit_gateway_route_table" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_route_table.this.arn
}

output "default_association_route_table" {
  description = "returns a bool"
  value       = data.aws_ec2_transit_gateway_route_table.this.default_association_route_table
}

output "default_propagation_route_table" {
  description = "returns a bool"
  value       = data.aws_ec2_transit_gateway_route_table.this.default_propagation_route_table
}

output "id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_route_table.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_transit_gateway_route_table.this.tags
}

output "transit_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_route_table.this.transit_gateway_id
}

output "this" {
  value = aws_ec2_transit_gateway_route_table.this
}
```

[top](#index)