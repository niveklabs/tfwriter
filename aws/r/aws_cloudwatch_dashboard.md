# aws_cloudwatch_dashboard

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

```hcl
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

```hcl
resource "aws_cloudwatch_dashboard" "this" {
  dashboard_body = var.dashboard_body
  dashboard_name = var.dashboard_name
}
```

[top](#index)

### Outputs

```hcl
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