# aws_ec2_local_gateway

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
module "aws_ec2_local_gateway" {
  source = "./modules/aws/d/aws_ec2_local_gateway"

  # state - (optional) is a type of string
  state = null
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
variable "state" {
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
      values = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_ec2_local_gateway" "this" {
  # state - (optional) is a type of string
  state = var.state
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = data.aws_ec2_local_gateway.this.id
}

output "outpost_arn" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway.this.outpost_arn
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway.this.owner_id
}

output "state" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_local_gateway.this.tags
}

output "this" {
  value = aws_ec2_local_gateway.this
}
```

[top](#index)