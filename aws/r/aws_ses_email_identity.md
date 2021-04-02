# aws_ses_email_identity

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
module "aws_ses_email_identity" {
  source = "./modules/aws/r/aws_ses_email_identity"

  # email - (required) is a type of string
  email = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ses_email_identity" "this" {
  email = var.email
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ses_email_identity.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_email_identity.this.id
}

output "this" {
  value = aws_ses_email_identity.this
}
```

[top](#index)