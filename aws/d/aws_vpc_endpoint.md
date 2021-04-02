# aws_vpc_endpoint

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
module "aws_vpc_endpoint" {
  source = "./modules/aws/d/aws_vpc_endpoint"

  # service_name - (optional) is a type of string
  service_name = null
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
variable "service_name" {
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
data "aws_vpc_endpoint" "this" {
  service_name = var.service_name
  state        = var.state
  tags         = var.tags
  vpc_id       = var.vpc_id

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
  value       = data.aws_vpc_endpoint.this.arn
}

output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.aws_vpc_endpoint.this.cidr_blocks
}

output "dns_entry" {
  description = "returns a list of object"
  value       = data.aws_vpc_endpoint.this.dns_entry
}

output "id" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.id
}

output "network_interface_ids" {
  description = "returns a set of string"
  value       = data.aws_vpc_endpoint.this.network_interface_ids
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.owner_id
}

output "policy" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.policy
}

output "prefix_list_id" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.prefix_list_id
}

output "private_dns_enabled" {
  description = "returns a bool"
  value       = data.aws_vpc_endpoint.this.private_dns_enabled
}

output "requester_managed" {
  description = "returns a bool"
  value       = data.aws_vpc_endpoint.this.requester_managed
}

output "route_table_ids" {
  description = "returns a set of string"
  value       = data.aws_vpc_endpoint.this.route_table_ids
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = data.aws_vpc_endpoint.this.security_group_ids
}

output "service_name" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.service_name
}

output "state" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.state
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = data.aws_vpc_endpoint.this.subnet_ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_vpc_endpoint.this.tags
}

output "vpc_endpoint_type" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.vpc_endpoint_type
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_vpc_endpoint.this.vpc_id
}

output "this" {
  value = aws_vpc_endpoint.this
}
```

[top](#index)