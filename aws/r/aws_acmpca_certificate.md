# aws_acmpca_certificate

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
module "aws_acmpca_certificate" {
  source = "./modules/aws/r/aws_acmpca_certificate"

  # certificate_authority_arn - (required) is a type of string
  certificate_authority_arn = null
  # certificate_signing_request - (required) is a type of string
  certificate_signing_request = null
  # signing_algorithm - (required) is a type of string
  signing_algorithm = null
  # template_arn - (optional) is a type of string
  template_arn = null

  validity = [{
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_authority_arn" {
  description = "(required)"
  type        = string
}

variable "certificate_signing_request" {
  description = "(required)"
  type        = string
}

variable "signing_algorithm" {
  description = "(required)"
  type        = string
}

variable "template_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "validity" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      type  = string
      value = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_acmpca_certificate" "this" {
  certificate_authority_arn   = var.certificate_authority_arn
  certificate_signing_request = var.certificate_signing_request
  signing_algorithm           = var.signing_algorithm
  template_arn                = var.template_arn

  dynamic "validity" {
    for_each = var.validity
    content {
      type  = validity.value["type"]
      value = validity.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_acmpca_certificate.this.arn
}

output "certificate" {
  description = "returns a string"
  value       = aws_acmpca_certificate.this.certificate
}

output "certificate_chain" {
  description = "returns a string"
  value       = aws_acmpca_certificate.this.certificate_chain
}

output "id" {
  description = "returns a string"
  value       = aws_acmpca_certificate.this.id
}

output "this" {
  value = aws_acmpca_certificate.this
}
```

[top](#index)