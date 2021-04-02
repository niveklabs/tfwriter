# aws_cloudwatch_log_stream

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
module "aws_cloudwatch_log_stream" {
  source = "./modules/aws/r/aws_cloudwatch_log_stream"

  # log_group_name - (required) is a type of string
  log_group_name = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "log_group_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_log_stream" "this" {
  log_group_name = var.log_group_name
  name           = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_log_stream.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_stream.this.id
}

output "this" {
  value = aws_cloudwatch_log_stream.this
}
```

[top](#index)