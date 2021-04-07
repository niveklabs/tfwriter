# aws_shield_protection

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
module "aws_shield_protection" {
  source = "./modules/aws/r/aws_shield_protection"

  # name - (required) is a type of string
  name = null
  # resource_arn - (required) is a type of string
  resource_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_shield_protection" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_arn - (required) is a type of string
  resource_arn = var.resource_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_shield_protection.this.id
}

output "this" {
  value = aws_shield_protection.this
}
```

[top](#index)