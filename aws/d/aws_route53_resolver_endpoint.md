# aws_route53_resolver_endpoint

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
module "aws_route53_resolver_endpoint" {
  source = "./modules/aws/d/aws_route53_resolver_endpoint"

  # resolver_endpoint_id - (optional) is a type of string
  resolver_endpoint_id = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "resolver_endpoint_id" {
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
data "aws_route53_resolver_endpoint" "this" {
  # resolver_endpoint_id - (optional) is a type of string
  resolver_endpoint_id = var.resolver_endpoint_id

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
output "arn" {
  description = "returns a string"
  value       = data.aws_route53_resolver_endpoint.this.arn
}

output "direction" {
  description = "returns a string"
  value       = data.aws_route53_resolver_endpoint.this.direction
}

output "id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_endpoint.this.id
}

output "ip_addresses" {
  description = "returns a set of string"
  value       = data.aws_route53_resolver_endpoint.this.ip_addresses
}

output "name" {
  description = "returns a string"
  value       = data.aws_route53_resolver_endpoint.this.name
}

output "status" {
  description = "returns a string"
  value       = data.aws_route53_resolver_endpoint.this.status
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_endpoint.this.vpc_id
}

output "this" {
  value = aws_route53_resolver_endpoint.this
}
```

[top](#index)