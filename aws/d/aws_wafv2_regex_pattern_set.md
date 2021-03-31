# aws_wafv2_regex_pattern_set

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_wafv2_regex_pattern_set" {
  source = "./modules/aws/d/aws_wafv2_regex_pattern_set"

  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_wafv2_regex_pattern_set" "this" {
  name  = var.name
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_wafv2_regex_pattern_set.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_wafv2_regex_pattern_set.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_wafv2_regex_pattern_set.this.id
}

output "regular_expression" {
  description = "returns a set of object"
  value       = data.aws_wafv2_regex_pattern_set.this.regular_expression
}

output "this" {
  value = aws_wafv2_regex_pattern_set.this
}
```

[top](#index)