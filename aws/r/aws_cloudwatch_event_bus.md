# aws_cloudwatch_event_bus

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_cloudwatch_event_bus" {
  source = "./modules/aws/r/aws_cloudwatch_event_bus"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_event_bus" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_event_bus.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_event_bus.this.id
}

output "this" {
  value = aws_cloudwatch_event_bus.this
}
```

[top](#index)