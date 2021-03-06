# aws_route_table

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
module "aws_route_table" {
  source = "./modules/aws/d/aws_route_table"

  # gateway_id - (optional) is a type of string
  gateway_id = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
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
variable "gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
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
data "aws_route_table" "this" {
  # gateway_id - (optional) is a type of string
  gateway_id = var.gateway_id
  # route_table_id - (optional) is a type of string
  route_table_id = var.route_table_id
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
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
  value       = data.aws_route_table.this.arn
}

output "associations" {
  description = "returns a list of object"
  value       = data.aws_route_table.this.associations
}

output "gateway_id" {
  description = "returns a string"
  value       = data.aws_route_table.this.gateway_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_route_table.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_route_table.this.owner_id
}

output "route_table_id" {
  description = "returns a string"
  value       = data.aws_route_table.this.route_table_id
}

output "routes" {
  description = "returns a list of object"
  value       = data.aws_route_table.this.routes
}

output "subnet_id" {
  description = "returns a string"
  value       = data.aws_route_table.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_route_table.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_route_table.this.vpc_id
}

output "this" {
  value = aws_route_table.this
}
```

[top](#index)