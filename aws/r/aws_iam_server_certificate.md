# aws_iam_server_certificate

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
module "aws_iam_server_certificate" {
  source = "./modules/aws/r/aws_iam_server_certificate"

  # certificate_body - (required) is a type of string
  certificate_body = null
  # certificate_chain - (optional) is a type of string
  certificate_chain = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path - (optional) is a type of string
  path = null
  # private_key - (required) is a type of string
  private_key = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "certificate_body" {
  description = "(required)"
  type        = string
}

variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
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
resource "aws_iam_server_certificate" "this" {
  # certificate_body - (required) is a type of string
  certificate_body = var.certificate_body
  # certificate_chain - (optional) is a type of string
  certificate_chain = var.certificate_chain
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # path - (optional) is a type of string
  path = var.path
  # private_key - (required) is a type of string
  private_key = var.private_key
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.arn
}

output "expiration" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.expiration
}

output "id" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.name
}

output "upload_date" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.upload_date
}

output "this" {
  value = aws_iam_server_certificate.this
}
```

[top](#index)