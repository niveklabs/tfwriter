# aws_iam_saml_provider

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
module "aws_iam_saml_provider" {
  source = "./modules/aws/r/aws_iam_saml_provider"

  # name - (required) is a type of string
  name = null
  # saml_metadata_document - (required) is a type of string
  saml_metadata_document = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "saml_metadata_document" {
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
resource "aws_iam_saml_provider" "this" {
  # name - (required) is a type of string
  name = var.name
  # saml_metadata_document - (required) is a type of string
  saml_metadata_document = var.saml_metadata_document
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_saml_provider.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_saml_provider.this.id
}

output "valid_until" {
  description = "returns a string"
  value       = aws_iam_saml_provider.this.valid_until
}

output "this" {
  value = aws_iam_saml_provider.this
}
```

[top](#index)