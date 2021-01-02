# aws_ec2_local_gateway_route_table_vpc_association

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
module "aws_ec2_local_gateway_route_table_vpc_association" {
  source = "./modules/aws/r/aws_ec2_local_gateway_route_table_vpc_association"

  # local_gateway_route_table_id - (required) is a type of string
  local_gateway_route_table_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "local_gateway_route_table_id" {
  description = "(required)"
  type        = string
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

```terraform
resource "aws_ec2_local_gateway_route_table_vpc_association" "this" {
  local_gateway_route_table_id = var.local_gateway_route_table_id
  tags                         = var.tags
  vpc_id                       = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_local_gateway_route_table_vpc_association.this.id
}

output "local_gateway_id" {
  description = "returns a string"
  value       = aws_ec2_local_gateway_route_table_vpc_association.this.local_gateway_id
}

output "this" {
  value = aws_ec2_local_gateway_route_table_vpc_association.this
}
```

[top](#index)