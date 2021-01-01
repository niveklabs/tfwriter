# aws_wafregional_size_constraint_set
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
module "aws_wafregional_size_constraint_set" {
  source = "./modules/aws/r/aws_wafregional_size_constraint_set"

  # name - (required) is a type of string
  name = null

  size_constraints = [{
    comparison_operator = null
    field_to_match = [{
      data = null
      type = null
    }]
    size                = null
    text_transformation = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "size_constraints" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      comparison_operator = string
      field_to_match = list(object(
        {
          data = string
          type = string
        }
      ))
      size                = number
      text_transformation = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_wafregional_size_constraint_set" "this" {
  name = var.name

  dynamic "size_constraints" {
    for_each = var.size_constraints
    content {
      comparison_operator = size_constraints.value["comparison_operator"]
      size                = size_constraints.value["size"]
      text_transformation = size_constraints.value["text_transformation"]

      dynamic "field_to_match" {
        for_each = size_constraints.value.field_to_match
        content {
          data = field_to_match.value["data"]
          type = field_to_match.value["type"]
        }
      }

    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_wafregional_size_constraint_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafregional_size_constraint_set.this.id
}

output "this" {
  value = aws_wafregional_size_constraint_set.this
}
```
[top](#index)
