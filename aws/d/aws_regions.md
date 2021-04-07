# aws_regions

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_regions" {
  source = "./modules/aws/d/aws_regions"

  # all_regions - (optional) is a type of bool
  all_regions = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "all_regions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_regions" "this" {
  # all_regions - (optional) is a type of bool
  all_regions = var.all_regions

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_regions.this.id
}

output "names" {
  description = "returns a set of string"
  value       = data.aws_regions.this.names
}

output "this" {
  value = aws_regions.this
}
```

[top](#index)