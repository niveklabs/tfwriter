# aws_ses_domain_identity_verification

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

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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

```terraform
resource "aws_ses_domain_identity_verification" "this" {
  # domain - (required) is a type of string
  domain = var.domain

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
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