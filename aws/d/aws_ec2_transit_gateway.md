# aws_ec2_transit_gateway

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
module "aws_ec2_transit_gateway" {
  source = "./modules/aws/d/aws_ec2_transit_gateway"

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
data "aws_ec2_transit_gateway" "this" {
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
output "amazon_side_asn" {
  description = "returns a number"
  value       = data.aws_ec2_transit_gateway.this.amazon_side_asn
}

output "arn" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.arn
}

output "association_default_route_table_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.association_default_route_table_id
}

output "auto_accept_shared_attachments" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.auto_accept_shared_attachments
}

output "default_route_table_association" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.default_route_table_association
}

output "default_route_table_propagation" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.default_route_table_propagation
}

output "description" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.description
}

output "dns_support" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.dns_support
}

output "id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.owner_id
}

output "propagation_default_route_table_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.propagation_default_route_table_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_transit_gateway.this.tags
}

output "vpn_ecmp_support" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway.this.vpn_ecmp_support
}

output "this" {
  value = aws_ec2_transit_gateway.this
}
```

[top](#index)