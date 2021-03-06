# aws_cloudfront_public_key

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
module "aws_cloudfront_public_key" {
  source = "./modules/aws/r/aws_cloudfront_public_key"

  # comment - (optional) is a type of string
  comment = null
  # encoded_key - (required) is a type of string
  encoded_key = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encoded_key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudfront_public_key" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # encoded_key - (required) is a type of string
  encoded_key = var.encoded_key
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
}
```

[top](#index)

### Outputs

```terraform
output "caller_reference" {
  description = "returns a string"
  value       = aws_cloudfront_public_key.this.caller_reference
}

output "etag" {
  description = "returns a string"
  value       = aws_cloudfront_public_key.this.etag
}

output "id" {
  description = "returns a string"
  value       = aws_cloudfront_public_key.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_cloudfront_public_key.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_cloudfront_public_key.this.name_prefix
}

output "this" {
  value = aws_cloudfront_public_key.this
}
```

[top](#index)