# aws_internet_gateway

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_internet_gateway" {
  source = "./modules/aws/r/aws_internet_gateway"

  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```hcl
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

```hcl
resource "aws_internet_gateway" "this" {
  tags   = var.tags
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_internet_gateway.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_internet_gateway.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_internet_gateway.this.owner_id
}

output "this" {
  value = aws_internet_gateway.this
}
```

[top](#index)