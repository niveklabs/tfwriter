# aws_lightsail_domain

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
module "aws_lightsail_domain" {
  source = "./modules/aws/r/aws_lightsail_domain"

  # domain_name - (required) is a type of string
  domain_name = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_lightsail_domain" "this" {
  domain_name = var.domain_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lightsail_domain.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_lightsail_domain.this.id
}

output "this" {
  value = aws_lightsail_domain.this
}
```

[top](#index)