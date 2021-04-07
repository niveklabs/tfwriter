# aws_acmpca_certificate_authority_certificate

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
module "aws_acmpca_certificate_authority_certificate" {
  source = "./modules/aws/r/aws_acmpca_certificate_authority_certificate"

  # certificate - (required) is a type of string
  certificate = null
  # certificate_authority_arn - (required) is a type of string
  certificate_authority_arn = null
  # certificate_chain - (optional) is a type of string
  certificate_chain = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate" {
  description = "(required)"
  type        = string
}

variable "certificate_authority_arn" {
  description = "(required)"
  type        = string
}

variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_acmpca_certificate_authority_certificate" "this" {
  # certificate - (required) is a type of string
  certificate = var.certificate
  # certificate_authority_arn - (required) is a type of string
  certificate_authority_arn = var.certificate_authority_arn
  # certificate_chain - (optional) is a type of string
  certificate_chain = var.certificate_chain
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority_certificate.this.id
}

output "this" {
  value = aws_acmpca_certificate_authority_certificate.this
}
```

[top](#index)