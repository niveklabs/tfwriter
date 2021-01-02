# aws_waf_regex_match_set

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
module "aws_waf_regex_match_set" {
  source = "./modules/aws/r/aws_waf_regex_match_set"

  # name - (required) is a type of string
  name = null

  regex_match_tuple = [{
    field_to_match = [{
      data = null
      type = null
    }]
    regex_pattern_set_id = null
    text_transformation  = null
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

variable "regex_match_tuple" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      field_to_match = list(object(
        {
          data = string
          type = string
        }
      ))
      regex_pattern_set_id = string
      text_transformation  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_waf_regex_match_set" "this" {
  name = var.name

  dynamic "regex_match_tuple" {
    for_each = var.regex_match_tuple
    content {
      regex_pattern_set_id = regex_match_tuple.value["regex_pattern_set_id"]
      text_transformation  = regex_match_tuple.value["text_transformation"]

      dynamic "field_to_match" {
        for_each = regex_match_tuple.value.field_to_match
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
  value       = aws_waf_regex_match_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_regex_match_set.this.id
}

output "this" {
  value = aws_waf_regex_match_set.this
}
```

[top](#index)