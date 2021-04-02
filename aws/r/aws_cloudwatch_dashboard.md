# aws_cloudwatch_dashboard

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
module "aws_cloudwatch_dashboard" {
  source = "./modules/aws/r/aws_cloudwatch_dashboard"

  # dashboard_body - (required) is a type of string
  dashboard_body = null
  # dashboard_name - (required) is a type of string
  dashboard_name = null
}
```

[top](#index)

### Variables

```terraform
variable "dashboard_body" {
  description = "(required)"
  type        = string
}

variable "dashboard_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_dashboard" "this" {
  dashboard_body = var.dashboard_body
  dashboard_name = var.dashboard_name
}
```

[top](#index)

### Outputs

```terraform
output "dashboard_arn" {
  description = "returns a string"
  value       = aws_cloudwatch_dashboard.this.dashboard_arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_dashboard.this.id
}

output "this" {
  value = aws_cloudwatch_dashboard.this
}
```

[top](#index)