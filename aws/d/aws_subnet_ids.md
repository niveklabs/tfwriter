# aws_subnet_ids

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
module "aws_subnet_ids" {
  source = "./modules/aws/d/aws_subnet_ids"

  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_subnet_ids" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of set of string
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
  value       = data.aws_subnet_ids.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_subnet_ids.this.ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_subnet_ids.this.tags
}

output "this" {
  value = aws_subnet_ids.this
}
```

[top](#index)