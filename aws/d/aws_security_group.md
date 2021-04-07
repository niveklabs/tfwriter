# aws_security_group

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
module "aws_security_group" {
  source = "./modules/aws/d/aws_security_group"

  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
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
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
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
data "aws_security_group" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (optional) is a type of string
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
output "arn" {
  description = "returns a string"
  value       = data.aws_security_group.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_security_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_security_group.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_security_group.this.name
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_security_group.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_security_group.this.vpc_id
}

output "this" {
  value = aws_security_group.this
}
```

[top](#index)