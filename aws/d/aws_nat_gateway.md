# aws_nat_gateway

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
module "aws_nat_gateway" {
  source = "./modules/aws/d/aws_nat_gateway"

  # state - (optional) is a type of string
  state = null
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
variable "state" {
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
data "aws_nat_gateway" "this" {
  state     = var.state
  subnet_id = var.subnet_id
  tags      = var.tags
  vpc_id    = var.vpc_id

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
output "allocation_id" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.allocation_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.id
}

output "network_interface_id" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.network_interface_id
}

output "private_ip" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.private_ip
}

output "public_ip" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.public_ip
}

output "state" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_nat_gateway.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_nat_gateway.this.vpc_id
}

output "this" {
  value = aws_nat_gateway.this
}
```

[top](#index)