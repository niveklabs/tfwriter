# aws_api_gateway_vpc_link

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
module "aws_api_gateway_vpc_link" {
  source = "./modules/aws/r/aws_api_gateway_vpc_link"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_arns - (required) is a type of list of string
  target_arns = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_arns" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_vpc_link" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target_arns - (required) is a type of list of string
  target_arns = var.target_arns
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_vpc_link.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_vpc_link.this.id
}

output "this" {
  value = aws_api_gateway_vpc_link.this
}
```

[top](#index)