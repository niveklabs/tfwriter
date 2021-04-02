# aws_wafregional_rule

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
module "aws_wafregional_rule" {
  source = "./modules/aws/r/aws_wafregional_rule"

  # metric_name - (required) is a type of string
  metric_name = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  predicate = [{
    data_id = null
    negated = null
    type    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "metric_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "predicate" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      data_id = string
      negated = bool
      type    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafregional_rule" "this" {
  metric_name = var.metric_name
  name        = var.name
  tags        = var.tags

  dynamic "predicate" {
    for_each = var.predicate
    content {
      data_id = predicate.value["data_id"]
      negated = predicate.value["negated"]
      type    = predicate.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_wafregional_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafregional_rule.this.id
}

output "this" {
  value = aws_wafregional_rule.this
}
```

[top](#index)