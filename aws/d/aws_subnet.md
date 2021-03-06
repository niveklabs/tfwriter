# aws_subnet

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
module "aws_subnet" {
  source = "./modules/aws/d/aws_subnet"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # availability_zone_id - (optional) is a type of string
  availability_zone_id = null
  # cidr_block - (optional) is a type of string
  cidr_block = null
  # default_for_az - (optional) is a type of bool
  default_for_az = null
  # ipv6_cidr_block - (optional) is a type of string
  ipv6_cidr_block = null
  # state - (optional) is a type of string
  state = null
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
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_for_az" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipv6_cidr_block" {
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
data "aws_subnet" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # availability_zone_id - (optional) is a type of string
  availability_zone_id = var.availability_zone_id
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # default_for_az - (optional) is a type of bool
  default_for_az = var.default_for_az
  # ipv6_cidr_block - (optional) is a type of string
  ipv6_cidr_block = var.ipv6_cidr_block
  # state - (optional) is a type of string
  state = var.state
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
  value       = data.aws_subnet.this.arn
}

output "assign_ipv6_address_on_creation" {
  description = "returns a bool"
  value       = data.aws_subnet.this.assign_ipv6_address_on_creation
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_subnet.this.availability_zone
}

output "availability_zone_id" {
  description = "returns a string"
  value       = data.aws_subnet.this.availability_zone_id
}

output "available_ip_address_count" {
  description = "returns a number"
  value       = data.aws_subnet.this.available_ip_address_count
}

output "cidr_block" {
  description = "returns a string"
  value       = data.aws_subnet.this.cidr_block
}

output "customer_owned_ipv4_pool" {
  description = "returns a string"
  value       = data.aws_subnet.this.customer_owned_ipv4_pool
}

output "default_for_az" {
  description = "returns a bool"
  value       = data.aws_subnet.this.default_for_az
}

output "id" {
  description = "returns a string"
  value       = data.aws_subnet.this.id
}

output "ipv6_cidr_block" {
  description = "returns a string"
  value       = data.aws_subnet.this.ipv6_cidr_block
}

output "ipv6_cidr_block_association_id" {
  description = "returns a string"
  value       = data.aws_subnet.this.ipv6_cidr_block_association_id
}

output "map_customer_owned_ip_on_launch" {
  description = "returns a bool"
  value       = data.aws_subnet.this.map_customer_owned_ip_on_launch
}

output "map_public_ip_on_launch" {
  description = "returns a bool"
  value       = data.aws_subnet.this.map_public_ip_on_launch
}

output "outpost_arn" {
  description = "returns a string"
  value       = data.aws_subnet.this.outpost_arn
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_subnet.this.owner_id
}

output "state" {
  description = "returns a string"
  value       = data.aws_subnet.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_subnet.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_subnet.this.vpc_id
}

output "this" {
  value = aws_subnet.this
}
```

[top](#index)