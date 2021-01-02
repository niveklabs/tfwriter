# aws_ec2_managed_prefix_list

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_managed_prefix_list" {
  source = "./modules/aws/d/aws_ec2_managed_prefix_list"

  # name - (optional) is a type of string
  name = null
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
data "aws_ec2_managed_prefix_list" "this" {
  name = var.name
  tags = var.tags

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
output "address_family" {
  description = "returns a string"
  value       = data.aws_ec2_managed_prefix_list.this.address_family
}

output "arn" {
  description = "returns a string"
  value       = data.aws_ec2_managed_prefix_list.this.arn
}

output "entries" {
  description = "returns a set of object"
  value       = data.aws_ec2_managed_prefix_list.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.aws_ec2_managed_prefix_list.this.id
}

output "max_entries" {
  description = "returns a number"
  value       = data.aws_ec2_managed_prefix_list.this.max_entries
}

output "name" {
  description = "returns a string"
  value       = data.aws_ec2_managed_prefix_list.this.name
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_ec2_managed_prefix_list.this.owner_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_managed_prefix_list.this.tags
}

output "version" {
  description = "returns a number"
  value       = data.aws_ec2_managed_prefix_list.this.version
}

output "this" {
  value = aws_ec2_managed_prefix_list.this
}
```

[top](#index)