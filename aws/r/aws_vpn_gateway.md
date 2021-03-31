# aws_vpn_gateway

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_vpn_gateway" {
  source = "./modules/aws/r/aws_vpn_gateway"

  # amazon_side_asn - (optional) is a type of string
  amazon_side_asn = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
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

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpn_gateway" "this" {
  amazon_side_asn   = var.amazon_side_asn
  availability_zone = var.availability_zone
  tags              = var.tags
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "amazon_side_asn" {
  description = "returns a string"
  value       = aws_vpn_gateway.this.amazon_side_asn
}

output "arn" {
  description = "returns a string"
  value       = aws_vpn_gateway.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_vpn_gateway.this.id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_vpn_gateway.this.vpc_id
}

output "this" {
  value = aws_vpn_gateway.this
}
```

[top](#index)