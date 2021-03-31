# aws_ec2_coip_pool

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_coip_pool" {
  source = "./modules/aws/d/aws_ec2_coip_pool"

  # local_gateway_route_table_id - (optional) is a type of string
  local_gateway_route_table_id = null
  # pool_id - (optional) is a type of string
  pool_id = null
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
variable "local_gateway_route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_id" {
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
data "aws_ec2_coip_pool" "this" {
  local_gateway_route_table_id = var.local_gateway_route_table_id
  pool_id                      = var.pool_id
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
  value       = data.aws_ec2_coip_pool.this.id
}

output "local_gateway_route_table_id" {
  description = "returns a string"
  value       = data.aws_ec2_coip_pool.this.local_gateway_route_table_id
}

output "pool_cidrs" {
  description = "returns a set of string"
  value       = data.aws_ec2_coip_pool.this.pool_cidrs
}

output "pool_id" {
  description = "returns a string"
  value       = data.aws_ec2_coip_pool.this.pool_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_coip_pool.this.tags
}

output "this" {
  value = aws_ec2_coip_pool.this
}
```

[top](#index)