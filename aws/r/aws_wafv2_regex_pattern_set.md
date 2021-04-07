# aws_wafv2_regex_pattern_set

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
module "aws_wafv2_regex_pattern_set" {
  source = "./modules/aws/r/aws_wafv2_regex_pattern_set"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
  # tags - (optional) is a type of map of string
  tags = {}

  regular_expression = [{
    regex_string = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "regular_expression" {
  description = "nested block: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      regex_string = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafv2_regex_pattern_set" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # scope - (required) is a type of string
  scope = var.scope
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "regular_expression" {
    for_each = var.regular_expression
    content {
      # regex_string - (required) is a type of string
      regex_string = regular_expression.value["regex_string"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_wafv2_regex_pattern_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafv2_regex_pattern_set.this.id
}

output "lock_token" {
  description = "returns a string"
  value       = aws_wafv2_regex_pattern_set.this.lock_token
}

output "this" {
  value = aws_wafv2_regex_pattern_set.this
}
```

[top](#index)