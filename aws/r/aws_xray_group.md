# aws_xray_group

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
module "aws_xray_group" {
  source = "./modules/aws/r/aws_xray_group"

  # filter_expression - (required) is a type of string
  filter_expression = null
  # group_name - (required) is a type of string
  group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "filter_expression" {
  description = "(required)"
  type        = string
}

variable "group_name" {
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
resource "aws_xray_group" "this" {
  # filter_expression - (required) is a type of string
  filter_expression = var.filter_expression
  # group_name - (required) is a type of string
  group_name = var.group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_xray_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_xray_group.this.id
}

output "this" {
  value = aws_xray_group.this
}
```

[top](#index)