# aws_acm_certificate

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_acm_certificate" {
  source = "./modules/aws/r/aws_acm_certificate"

  # certificate_authority_arn - (optional) is a type of string
  certificate_authority_arn = null
  # certificate_body - (optional) is a type of string
  certificate_body = null
  # certificate_chain - (optional) is a type of string
  certificate_chain = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # private_key - (optional) is a type of string
  private_key = null
  # subject_alternative_names - (optional) is a type of set of string
  subject_alternative_names = []
  # tags - (optional) is a type of map of string
  tags = {}
  # validation_method - (optional) is a type of string
  validation_method = null

  options = [{
    certificate_transparency_logging_preference = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "certificate_authority_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_alternative_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "validation_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_transparency_logging_preference = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_acm_certificate" "this" {
  certificate_authority_arn = var.certificate_authority_arn
  certificate_body          = var.certificate_body
  certificate_chain         = var.certificate_chain
  domain_name               = var.domain_name
  private_key               = var.private_key
  subject_alternative_names = var.subject_alternative_names
  tags                      = var.tags
  validation_method         = var.validation_method

  dynamic "options" {
    for_each = var.options
    content {
      certificate_transparency_logging_preference = options.value["certificate_transparency_logging_preference"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_acm_certificate.this.arn
}

output "domain_name" {
  description = "returns a string"
  value       = aws_acm_certificate.this.domain_name
}

output "domain_validation_options" {
  description = "returns a set of object"
  value       = aws_acm_certificate.this.domain_validation_options
}

output "id" {
  description = "returns a string"
  value       = aws_acm_certificate.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_acm_certificate.this.status
}

output "subject_alternative_names" {
  description = "returns a set of string"
  value       = aws_acm_certificate.this.subject_alternative_names
}

output "validation_emails" {
  description = "returns a list of string"
  value       = aws_acm_certificate.this.validation_emails
}

output "validation_method" {
  description = "returns a string"
  value       = aws_acm_certificate.this.validation_method
}

output "this" {
  value = aws_acm_certificate.this
}
```

[top](#index)