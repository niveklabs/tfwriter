# aws_wafregional_geo_match_set

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
module "aws_wafregional_geo_match_set" {
  source = "./modules/aws/r/aws_wafregional_geo_match_set"

  # name - (required) is a type of string
  name = null

  geo_match_constraint = [{
    type  = null
    value = null
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

variable "geo_match_constraint" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafregional_geo_match_set" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "geo_match_constraint" {
    for_each = var.geo_match_constraint
    content {
      # type - (required) is a type of string
      type = geo_match_constraint.value["type"]
      # value - (required) is a type of string
      value = geo_match_constraint.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_wafregional_geo_match_set.this.id
}

output "this" {
  value = aws_wafregional_geo_match_set.this
}
```

[top](#index)