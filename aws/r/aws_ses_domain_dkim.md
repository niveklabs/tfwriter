# aws_ses_domain_dkim

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
module "aws_ses_domain_dkim" {
  source = "./modules/aws/r/aws_ses_domain_dkim"

  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```hcl
variable "domain" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_domain_dkim" "this" {
  domain = var.domain
}
```

[top](#index)

### Outputs

```hcl
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