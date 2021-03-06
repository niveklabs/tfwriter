# aws_waf_xss_match_set

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
module "aws_waf_xss_match_set" {
  source = "./modules/aws/r/aws_waf_xss_match_set"

  # name - (required) is a type of string
  name = null

  xss_match_tuples = [{
    field_to_match = [{
      data = null
      type = null
    }]
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

variable "xss_match_tuples" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      field_to_match = list(object(
        {
          data = string
          type = string
        }
      ))
      text_transformation = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_waf_xss_match_set" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "xss_match_tuples" {
    for_each = var.xss_match_tuples
    content {
      # text_transformation - (required) is a type of string
      text_transformation = xss_match_tuples.value["text_transformation"]

      dynamic "field_to_match" {
        for_each = xss_match_tuples.value.field_to_match
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
output "arn" {
  description = "returns a string"
  value       = aws_waf_xss_match_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_xss_match_set.this.id
}

output "this" {
  value = aws_waf_xss_match_set.this
}
```

[top](#index)