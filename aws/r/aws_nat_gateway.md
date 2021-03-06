# aws_nat_gateway

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
module "aws_nat_gateway" {
  source = "./modules/aws/r/aws_nat_gateway"

  # allocation_id - (required) is a type of string
  allocation_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "allocation_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
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
resource "aws_nat_gateway" "this" {
  # allocation_id - (required) is a type of string
  allocation_id = var.allocation_id
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_nat_gateway.this.id
}

output "network_interface_id" {
  description = "returns a string"
  value       = aws_nat_gateway.this.network_interface_id
}

output "private_ip" {
  description = "returns a string"
  value       = aws_nat_gateway.this.private_ip
}

output "public_ip" {
  description = "returns a string"
  value       = aws_nat_gateway.this.public_ip
}

output "this" {
  value = aws_nat_gateway.this
}
```

[top](#index)