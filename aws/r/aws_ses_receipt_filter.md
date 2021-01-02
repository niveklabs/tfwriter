# aws_ses_receipt_filter

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
module "aws_ses_receipt_filter" {
  source = "./modules/aws/r/aws_ses_receipt_filter"

  # cidr - (required) is a type of string
  cidr = null
  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ses_receipt_filter" "this" {
  cidr   = var.cidr
  name   = var.name
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ses_receipt_filter.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_receipt_filter.this.id
}

output "this" {
  value = aws_ses_receipt_filter.this
}
```

[top](#index)