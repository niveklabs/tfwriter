# aws_vpn_gateway

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_vpn_gateway" {
  source = "./modules/aws/d/aws_vpn_gateway"

  # amazon_side_asn - (optional) is a type of string
  amazon_side_asn = null
  # attached_vpc_id - (optional) is a type of string
  attached_vpc_id = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # state - (optional) is a type of string
  state = null
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
variable "amazon_side_asn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attached_vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

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
      values = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_vpn_gateway" "this" {
  amazon_side_asn   = var.amazon_side_asn
  attached_vpc_id   = var.attached_vpc_id
  availability_zone = var.availability_zone
  state             = var.state
  tags              = var.tags

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
output "amazon_side_asn" {
  description = "returns a string"
  value       = data.aws_vpn_gateway.this.amazon_side_asn
}

output "arn" {
  description = "returns a string"
  value       = data.aws_vpn_gateway.this.arn
}

output "attached_vpc_id" {
  description = "returns a string"
  value       = data.aws_vpn_gateway.this.attached_vpc_id
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_vpn_gateway.this.availability_zone
}

output "id" {
  description = "returns a string"
  value       = data.aws_vpn_gateway.this.id
}

output "state" {
  description = "returns a string"
  value       = data.aws_vpn_gateway.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_vpn_gateway.this.tags
}

output "this" {
  value = aws_vpn_gateway.this
}
```

[top](#index)