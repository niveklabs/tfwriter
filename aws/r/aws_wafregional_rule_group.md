# aws_wafregional_rule_group

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
module "aws_wafregional_rule_group" {
  source = "./modules/aws/r/aws_wafregional_rule_group"

  # metric_name - (required) is a type of string
  metric_name = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  activated_rule = [{
    action = [{
      type = null
    }]
    priority = null
    rule_id  = null
    type     = null
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

variable "activated_rule" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          type = string
        }
      ))
      priority = number
      rule_id  = string
      type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafregional_rule_group" "this" {
  metric_name = var.metric_name
  name        = var.name
  tags        = var.tags

  dynamic "activated_rule" {
    for_each = var.activated_rule
    content {
      priority = activated_rule.value["priority"]
      rule_id  = activated_rule.value["rule_id"]
      type     = activated_rule.value["type"]

      dynamic "action" {
        for_each = activated_rule.value.action
        content {
          type = action.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_wafregional_rule_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafregional_rule_group.this.id
}

output "this" {
  value = aws_wafregional_rule_group.this
}
```

[top](#index)