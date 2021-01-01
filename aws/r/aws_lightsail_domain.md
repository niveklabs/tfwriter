# aws_lightsail_domain

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
module "aws_lightsail_domain" {
  source = "./modules/aws/r/aws_lightsail_domain"

  # domain_name - (required) is a type of string
  domain_name = null
}
```

[top](#index)

### Variables

```hcl
variable "domain_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_lightsail_domain" "this" {
  domain_name = var.domain_name
}
```

[top](#index)

### Outputs

```hcl
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