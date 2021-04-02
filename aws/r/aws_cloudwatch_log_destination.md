# aws_cloudwatch_log_destination

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
module "aws_cloudwatch_log_destination" {
  source = "./modules/aws/r/aws_cloudwatch_log_destination"

  # name - (required) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # target_arn - (required) is a type of string
  target_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "target_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_log_destination" "this" {
  name       = var.name
  role_arn   = var.role_arn
  target_arn = var.target_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_log_destination.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_destination.this.id
}

output "this" {
  value = aws_cloudwatch_log_destination.this
}
```

[top](#index)