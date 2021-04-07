# aws_wafregional_byte_match_set

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
module "aws_wafregional_byte_match_set" {
  source = "./modules/aws/r/aws_wafregional_byte_match_set"

  # name - (required) is a type of string
  name = null

  byte_match_tuples = [{
    field_to_match = [{
      data = null
      type = null
    }]
    positional_constraint = null
    target_string         = null
    text_transformation   = null
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

variable "byte_match_tuples" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      field_to_match = list(object(
        {
          data = string
          type = string
        }
      ))
      positional_constraint = string
      target_string         = string
      text_transformation   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafregional_byte_match_set" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "byte_match_tuples" {
    for_each = var.byte_match_tuples
    content {
      # positional_constraint - (required) is a type of string
      positional_constraint = byte_match_tuples.value["positional_constraint"]
      # target_string - (optional) is a type of string
      target_string = byte_match_tuples.value["target_string"]
      # text_transformation - (required) is a type of string
      text_transformation = byte_match_tuples.value["text_transformation"]

      dynamic "field_to_match" {
        for_each = byte_match_tuples.value.field_to_match
        content {
          # data - (optional) is a type of string
          data = field_to_match.value["data"]
          # type - (required) is a type of string
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
output "id" {
  description = "returns a string"
  value       = aws_wafregional_byte_match_set.this.id
}

output "this" {
  value = aws_wafregional_byte_match_set.this
}
```

[top](#index)