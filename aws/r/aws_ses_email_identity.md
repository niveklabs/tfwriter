# aws_ses_email_identity

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_ses_email_identity" {
  source = "./modules/aws/r/aws_ses_email_identity"

  # email - (required) is a type of string
  email = null
}
```

[top](#index)

### Variables

```hcl
variable "email" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_email_identity" "this" {
  email = var.email
}
```

[top](#index)

### Outputs

```hcl
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