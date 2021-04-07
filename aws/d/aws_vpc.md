# aws_vpc

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
module "aws_vpc" {
  source = "./modules/aws/d/aws_vpc"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # default - (optional) is a type of bool
  default = null
  # dhcp_options_id - (optional) is a type of string
  dhcp_options_id = null
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
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dhcp_options_id" {
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
data "aws_vpc" "this" {
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # default - (optional) is a type of bool
  default = var.default
  # dhcp_options_id - (optional) is a type of string
  dhcp_options_id = var.dhcp_options_id
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
output "arn" {
  description = "returns a string"
  value       = data.aws_vpc.this.arn
}

output "cidr_block" {
  description = "returns a string"
  value       = data.aws_vpc.this.cidr_block
}

output "cidr_block_associations" {
  description = "returns a list of object"
  value       = data.aws_vpc.this.cidr_block_associations
}

output "default" {
  description = "returns a bool"
  value       = data.aws_vpc.this.default
}

output "dhcp_options_id" {
  description = "returns a string"
  value       = data.aws_vpc.this.dhcp_options_id
}

output "enable_dns_hostnames" {
  description = "returns a bool"
  value       = data.aws_vpc.this.enable_dns_hostnames
}

output "enable_dns_support" {
  description = "returns a bool"
  value       = data.aws_vpc.this.enable_dns_support
}

output "id" {
  description = "returns a string"
  value       = data.aws_vpc.this.id
}

output "instance_tenancy" {
  description = "returns a string"
  value       = data.aws_vpc.this.instance_tenancy
}

output "ipv6_association_id" {
  description = "returns a string"
  value       = data.aws_vpc.this.ipv6_association_id
}

output "ipv6_cidr_block" {
  description = "returns a string"
  value       = data.aws_vpc.this.ipv6_cidr_block
}

output "main_route_table_id" {
  description = "returns a string"
  value       = data.aws_vpc.this.main_route_table_id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_vpc.this.owner_id
}

output "state" {
  description = "returns a string"
  value       = data.aws_vpc.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_vpc.this.tags
}

output "this" {
  value = aws_vpc.this
}
```

[top](#index)