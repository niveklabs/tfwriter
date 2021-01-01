# aws_ec2_local_gateway_route_tables

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_ec2_local_gateway_route_tables" {
  source = "./modules/aws/d/aws_ec2_local_gateway_route_tables"

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

```hcl
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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

```hcl
data "aws_ec2_local_gateway_route_tables" "this" {
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

```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_route_tables.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_ec2_local_gateway_route_tables.this.ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_local_gateway_route_tables.this.tags
}

output "this" {
  value = aws_ec2_local_gateway_route_tables.this
}
```

[top](#index)