# aws_waf_geo_match_set

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_waf_geo_match_set" {
  source = "./modules/aws/r/aws_waf_geo_match_set"

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

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "geo_match_constraint" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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

```hcl
resource "aws_waf_geo_match_set" "this" {
  name = var.name

  dynamic "geo_match_constraint" {
    for_each = var.geo_match_constraint
    content {
      type  = geo_match_constraint.value["type"]
      value = geo_match_constraint.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_waf_geo_match_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_geo_match_set.this.id
}

output "this" {
  value = aws_waf_geo_match_set.this
}
```

[top](#index)