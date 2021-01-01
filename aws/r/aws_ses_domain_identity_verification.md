# aws_ses_domain_identity_verification

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
module "aws_ses_domain_identity_verification" {
  source = "./modules/aws/r/aws_ses_domain_identity_verification"

  # domain - (required) is a type of string
  domain = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "domain" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_domain_identity_verification" "this" {
  domain = var.domain

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ses_domain_identity_verification.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_domain_identity_verification.this.id
}

output "this" {
  value = aws_ses_domain_identity_verification.this
}
```

[top](#index)