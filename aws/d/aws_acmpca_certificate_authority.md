# aws_acmpca_certificate_authority

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
module "aws_acmpca_certificate_authority" {
  source = "./modules/aws/d/aws_acmpca_certificate_authority"

  # arn - (required) is a type of string
  arn = null
  # tags - (optional) is a type of map of string
  tags = {}

  revocation_configuration = [{
    crl_configuration = [{
      custom_cname       = null
      enabled            = null
      expiration_in_days = null
      s3_bucket_name     = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "revocation_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      crl_configuration = list(object(
        {
          custom_cname       = string
          enabled            = bool
          expiration_in_days = number
          s3_bucket_name     = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_acmpca_certificate_authority" "this" {
  # arn - (required) is a type of string
  arn = var.arn
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "revocation_configuration" {
    for_each = var.revocation_configuration
    content {

      dynamic "crl_configuration" {
        for_each = revocation_configuration.value.crl_configuration
        content {
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.certificate
}

output "certificate_chain" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.certificate_chain
}

output "certificate_signing_request" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.certificate_signing_request
}

output "id" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.id
}

output "not_after" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.not_after
}

output "not_before" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.not_before
}

output "serial" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.serial
}

output "status" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_acmpca_certificate_authority.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.aws_acmpca_certificate_authority.this.type
}

output "this" {
  value = aws_acmpca_certificate_authority.this
}
```

[top](#index)