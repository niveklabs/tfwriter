# aws_securityhub_product_subscription

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_securityhub_product_subscription" {
  source = "./modules/aws/r/aws_securityhub_product_subscription"

  # product_arn - (required) is a type of string
  product_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "product_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_securityhub_product_subscription" "this" {
  product_arn = var.product_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_securityhub_product_subscription.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_securityhub_product_subscription.this.id
}

output "this" {
  value = aws_securityhub_product_subscription.this
}
```

[top](#index)