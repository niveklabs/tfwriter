# aws_vpc_endpoint

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_vpc_endpoint" {
  source = "./modules/aws/r/aws_vpc_endpoint"

  # auto_accept - (optional) is a type of bool
  auto_accept = null
  # policy - (optional) is a type of string
  policy = null
  # private_dns_enabled - (optional) is a type of bool
  private_dns_enabled = null
  # route_table_ids - (optional) is a type of set of string
  route_table_ids = []
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # service_name - (required) is a type of string
  service_name = null
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_endpoint_type - (optional) is a type of string
  vpc_endpoint_type = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_accept" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_dns_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "route_table_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "subnet_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_endpoint_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc_endpoint" "this" {
  auto_accept         = var.auto_accept
  policy              = var.policy
  private_dns_enabled = var.private_dns_enabled
  route_table_ids     = var.route_table_ids
  security_group_ids  = var.security_group_ids
  service_name        = var.service_name
  subnet_ids          = var.subnet_ids
  tags                = var.tags
  vpc_endpoint_type   = var.vpc_endpoint_type
  vpc_id              = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_vpc_endpoint.this.arn
}

output "cidr_blocks" {
  description = "returns a list of string"
  value       = aws_vpc_endpoint.this.cidr_blocks
}

output "dns_entry" {
  description = "returns a list of object"
  value       = aws_vpc_endpoint.this.dns_entry
}

output "id" {
  description = "returns a string"
  value       = aws_vpc_endpoint.this.id
}

output "network_interface_ids" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint.this.network_interface_ids
}

output "owner_id" {
  description = "returns a string"
  value       = aws_vpc_endpoint.this.owner_id
}

output "policy" {
  description = "returns a string"
  value       = aws_vpc_endpoint.this.policy
}

output "prefix_list_id" {
  description = "returns a string"
  value       = aws_vpc_endpoint.this.prefix_list_id
}

output "requester_managed" {
  description = "returns a bool"
  value       = aws_vpc_endpoint.this.requester_managed
}

output "route_table_ids" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint.this.route_table_ids
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint.this.security_group_ids
}

output "state" {
  description = "returns a string"
  value       = aws_vpc_endpoint.this.state
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = aws_vpc_endpoint.this.subnet_ids
}

output "this" {
  value = aws_vpc_endpoint.this
}
```

[top](#index)