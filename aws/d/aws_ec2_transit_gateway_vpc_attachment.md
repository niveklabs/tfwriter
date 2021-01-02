# aws_ec2_transit_gateway_vpc_attachment

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_transit_gateway_vpc_attachment" {
  source = "./modules/aws/d/aws_ec2_transit_gateway_vpc_attachment"

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
data "aws_ec2_transit_gateway_vpc_attachment" "this" {
  tags = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "appliance_mode_support" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.appliance_mode_support
}

output "dns_support" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.dns_support
}

output "id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.id
}

output "ipv6_support" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.ipv6_support
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.subnet_ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.tags
}

output "transit_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.transit_gateway_id
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.vpc_id
}

output "vpc_owner_id" {
  description = "returns a string"
  value       = data.aws_ec2_transit_gateway_vpc_attachment.this.vpc_owner_id
}

output "this" {
  value = aws_ec2_transit_gateway_vpc_attachment.this
}
```

[top](#index)