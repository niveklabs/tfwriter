# aws_ec2_local_gateway_route_table

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
module "aws_ec2_local_gateway_route_table" {
  source = "./modules/aws/d/aws_ec2_local_gateway_route_table"

  # local_gateway_id - (optional) is a type of string
  local_gateway_id = null
  # local_gateway_route_table_id - (optional) is a type of string
  local_gateway_route_table_id = null
  # outpost_arn - (optional) is a type of string
  outpost_arn = null
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
variable "local_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_gateway_route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outpost_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

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
data "aws_ec2_local_gateway_route_table" "this" {
  local_gateway_id             = var.local_gateway_id
  local_gateway_route_table_id = var.local_gateway_route_table_id
  outpost_arn                  = var.outpost_arn
  state                        = var.state
  tags                         = var.tags

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
output "id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_route_table.this.id
}

output "local_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_route_table.this.local_gateway_id
}

output "local_gateway_route_table_id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_route_table.this.local_gateway_route_table_id
}

output "outpost_arn" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_route_table.this.outpost_arn
}

output "state" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_route_table.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_local_gateway_route_table.this.tags
}

output "this" {
  value = aws_ec2_local_gateway_route_table.this
}
```

[top](#index)