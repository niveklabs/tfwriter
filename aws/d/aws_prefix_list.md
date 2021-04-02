# aws_prefix_list

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
module "aws_prefix_list" {
  source = "./modules/aws/d/aws_prefix_list"

  # name - (optional) is a type of string
  name = null
  # prefix_list_id - (optional) is a type of string
  prefix_list_id = null

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

variable "prefix_list_id" {
  description = "(optional)"
  type        = string
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
data "aws_prefix_list" "this" {
  name           = var.name
  prefix_list_id = var.prefix_list_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.aws_prefix_list.this.cidr_blocks
}

output "id" {
  description = "returns a string"
  value       = data.aws_prefix_list.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_prefix_list.this.name
}

output "this" {
  value = aws_prefix_list.this
}
```

[top](#index)