# aws_internet_gateway

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
module "aws_internet_gateway" {
  source = "./modules/aws/d/aws_internet_gateway"

  # internet_gateway_id - (optional) is a type of string
  internet_gateway_id = null
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
variable "internet_gateway_id" {
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

```terraform
data "aws_internet_gateway" "this" {
  internet_gateway_id = var.internet_gateway_id
  tags                = var.tags

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
  value       = data.aws_internet_gateway.this.arn
}

output "attachments" {
  description = "returns a list of object"
  value       = data.aws_internet_gateway.this.attachments
}

output "id" {
  description = "returns a string"
  value       = data.aws_internet_gateway.this.id
}

output "internet_gateway_id" {
  description = "returns a string"
  value       = data.aws_internet_gateway.this.internet_gateway_id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_internet_gateway.this.owner_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_internet_gateway.this.tags
}

output "this" {
  value = aws_internet_gateway.this
}
```

[top](#index)