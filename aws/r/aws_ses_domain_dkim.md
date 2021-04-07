# aws_ses_domain_dkim

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
module "aws_ses_domain_dkim" {
  source = "./modules/aws/r/aws_ses_domain_dkim"

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
resource "aws_ses_domain_dkim" "this" {
  # domain - (required) is a type of string
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "dkim_tokens" {
  description = "returns a list of string"
  value       = aws_ses_domain_dkim.this.dkim_tokens
}

output "id" {
  description = "returns a string"
  value       = aws_ses_domain_dkim.this.id
}

output "this" {
  value = aws_ses_domain_dkim.this
}
```

[top](#index)