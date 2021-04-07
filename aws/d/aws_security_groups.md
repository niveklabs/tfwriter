# aws_security_groups

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
module "aws_security_groups" {
  source = "./modules/aws/d/aws_security_groups"

  # tags - (optional) is a type of map of string
  tags = {}

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
data "aws_security_groups" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "arns" {
  description = "returns a list of string"
  value       = data.aws_security_groups.this.arns
}

output "id" {
  description = "returns a string"
  value       = data.aws_security_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.aws_security_groups.this.ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_security_groups.this.tags
}

output "vpc_ids" {
  description = "returns a list of string"
  value       = data.aws_security_groups.this.vpc_ids
}

output "this" {
  value = aws_security_groups.this
}
```

[top](#index)