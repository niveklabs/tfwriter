# aws_customer_gateway

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
module "aws_customer_gateway" {
  source = "./modules/aws/d/aws_customer_gateway"

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
data "aws_customer_gateway" "this" {
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
output "arn" {
  description = "returns a string"
  value       = data.aws_customer_gateway.this.arn
}

output "bgp_asn" {
  description = "returns a number"
  value       = data.aws_customer_gateway.this.bgp_asn
}

output "device_name" {
  description = "returns a string"
  value       = data.aws_customer_gateway.this.device_name
}

output "id" {
  description = "returns a string"
  value       = data.aws_customer_gateway.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.aws_customer_gateway.this.ip_address
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_customer_gateway.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.aws_customer_gateway.this.type
}

output "this" {
  value = aws_customer_gateway.this
}
```

[top](#index)