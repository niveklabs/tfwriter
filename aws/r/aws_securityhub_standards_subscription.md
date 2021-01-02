# aws_securityhub_standards_subscription

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
module "aws_securityhub_standards_subscription" {
  source = "./modules/aws/r/aws_securityhub_standards_subscription"

  # standards_arn - (required) is a type of string
  standards_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "standards_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_securityhub_standards_subscription" "this" {
  standards_arn = var.standards_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_securityhub_standards_subscription.this.id
}

output "this" {
  value = aws_securityhub_standards_subscription.this
}
```

[top](#index)