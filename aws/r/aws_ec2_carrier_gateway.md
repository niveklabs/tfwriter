# aws_ec2_carrier_gateway

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
module "aws_ec2_carrier_gateway" {
  source = "./modules/aws/r/aws_ec2_carrier_gateway"

  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
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

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_carrier_gateway" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ec2_carrier_gateway.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_carrier_gateway.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ec2_carrier_gateway.this.owner_id
}

output "this" {
  value = aws_ec2_carrier_gateway.this
}
```

[top](#index)