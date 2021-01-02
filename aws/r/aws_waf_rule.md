# aws_waf_rule

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
module "aws_waf_rule" {
  source = "./modules/aws/r/aws_waf_rule"

  # metric_name - (required) is a type of string
  metric_name = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  predicates = [{
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

variable "predicates" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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
resource "aws_waf_rule" "this" {
  metric_name = var.metric_name
  name        = var.name
  tags        = var.tags

  dynamic "predicates" {
    for_each = var.predicates
    content {
      data_id = predicates.value["data_id"]
      negated = predicates.value["negated"]
      type    = predicates.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_waf_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_rule.this.id
}

output "this" {
  value = aws_waf_rule.this
}
```

[top](#index)