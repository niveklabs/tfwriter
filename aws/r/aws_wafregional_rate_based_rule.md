# aws_wafregional_rate_based_rule
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
module "aws_wafregional_rate_based_rule" {
  source = "./modules/aws/r/aws_wafregional_rate_based_rule"

  # metric_name - (required) is a type of string
  metric_name = null
  # name - (required) is a type of string
  name = null
  # rate_key - (required) is a type of string
  rate_key = null
  # rate_limit - (required) is a type of number
  rate_limit = null
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
```hcl
variable "metric_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rate_key" {
  description = "(required)"
  type        = string
}

variable "rate_limit" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "predicate" {
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
```hcl
resource "aws_wafregional_rate_based_rule" "this" {
  metric_name = var.metric_name
  name        = var.name
  rate_key    = var.rate_key
  rate_limit  = var.rate_limit
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
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_wafregional_rate_based_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafregional_rate_based_rule.this.id
}

output "this" {
  value = aws_wafregional_rate_based_rule.this
}
```
[top](#index)
