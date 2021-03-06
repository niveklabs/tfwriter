# aws_placement_group

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
module "aws_placement_group" {
  source = "./modules/aws/r/aws_placement_group"

  # name - (required) is a type of string
  name = null
  # strategy - (required) is a type of string
  strategy = null
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

variable "strategy" {
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
resource "aws_placement_group" "this" {
  # name - (required) is a type of string
  name = var.name
  # strategy - (required) is a type of string
  strategy = var.strategy
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_placement_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_placement_group.this.id
}

output "placement_group_id" {
  description = "returns a string"
  value       = aws_placement_group.this.placement_group_id
}

output "this" {
  value = aws_placement_group.this
}
```

[top](#index)