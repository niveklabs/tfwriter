# aws_acmpca_certificate

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aws/d/aws_acmpca_certificate"

  # arn - (required) is a type of string
  arn = null
  # certificate_authority_arn - (required) is a type of string
  certificate_authority_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "certificate_authority_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_acmpca_certificate" "this" {
  arn                       = var.arn
  certificate_authority_arn = var.certificate_authority_arn
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate.this.certificate
}

output "certificate_chain" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate.this.certificate_chain
}

output "id" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate.this.id
}

output "this" {
  value = aws_acmpca_certificate.this
}
```

[top](#index)