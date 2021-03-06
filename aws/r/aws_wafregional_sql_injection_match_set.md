# aws_wafregional_sql_injection_match_set

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
module "aws_wafregional_sql_injection_match_set" {
  source = "./modules/aws/r/aws_wafregional_sql_injection_match_set"

  # name - (required) is a type of string
  name = null

  sql_injection_match_tuple = [{
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

variable "sql_injection_match_tuple" {
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
resource "aws_wafregional_sql_injection_match_set" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "sql_injection_match_tuple" {
    for_each = var.sql_injection_match_tuple
    content {
      # text_transformation - (required) is a type of string
      text_transformation = sql_injection_match_tuple.value["text_transformation"]

      dynamic "field_to_match" {
        for_each = sql_injection_match_tuple.value.field_to_match
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
  value       = aws_wafregional_sql_injection_match_set.this.id
}

output "this" {
  value = aws_wafregional_sql_injection_match_set.this
}
```

[top](#index)