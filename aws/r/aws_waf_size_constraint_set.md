# aws_waf_size_constraint_set

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
module "aws_waf_size_constraint_set" {
  source = "./modules/aws/r/aws_waf_size_constraint_set"

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

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "size_constraints" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
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

```terraform
resource "aws_waf_size_constraint_set" "this" {
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

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_waf_size_constraint_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_size_constraint_set.this.id
}

output "this" {
  value = aws_waf_size_constraint_set.this
}
```

[top](#index)