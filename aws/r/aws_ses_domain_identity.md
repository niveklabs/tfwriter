# aws_ses_domain_identity

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
module "aws_ses_domain_identity" {
  source = "./modules/aws/r/aws_ses_domain_identity"

  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ses_domain_identity" "this" {
  # domain - (required) is a type of string
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ses_domain_identity.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_domain_identity.this.id
}

output "verification_token" {
  description = "returns a string"
  value       = aws_ses_domain_identity.this.verification_token
}

output "this" {
  value = aws_ses_domain_identity.this
}
```

[top](#index)