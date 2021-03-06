# aws_vpc

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_vpc" {
  source = "./modules/aws/r/aws_vpc"

  # assign_generated_ipv6_cidr_block - (optional) is a type of bool
  assign_generated_ipv6_cidr_block = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # enable_classiclink - (optional) is a type of bool
  enable_classiclink = null
  # enable_classiclink_dns_support - (optional) is a type of bool
  enable_classiclink_dns_support = null
  # enable_dns_hostnames - (optional) is a type of bool
  enable_dns_hostnames = null
  # enable_dns_support - (optional) is a type of bool
  enable_dns_support = null
  # instance_tenancy - (optional) is a type of string
  instance_tenancy = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tags_all - (optional) is a type of map of string
  tags_all = {}
}
```

[top](#index)

### Variables

```terraform
variable "assign_generated_ipv6_cidr_block" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "enable_classiclink" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_classiclink_dns_support" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_dns_hostnames" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_dns_support" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_tenancy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags_all" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc" "this" {
  # assign_generated_ipv6_cidr_block - (optional) is a type of bool
  assign_generated_ipv6_cidr_block = var.assign_generated_ipv6_cidr_block
  # cidr_block - (required) is a type of string
  cidr_block = var.cidr_block
  # enable_classiclink - (optional) is a type of bool
  enable_classiclink = var.enable_classiclink
  # enable_classiclink_dns_support - (optional) is a type of bool
  enable_classiclink_dns_support = var.enable_classiclink_dns_support
  # enable_dns_hostnames - (optional) is a type of bool
  enable_dns_hostnames = var.enable_dns_hostnames
  # enable_dns_support - (optional) is a type of bool
  enable_dns_support = var.enable_dns_support
  # instance_tenancy - (optional) is a type of string
  instance_tenancy = var.instance_tenancy
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tags_all - (optional) is a type of map of string
  tags_all = var.tags_all
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_vpc.this.arn
}

output "default_network_acl_id" {
  description = "returns a string"
  value       = aws_vpc.this.default_network_acl_id
}

output "default_route_table_id" {
  description = "returns a string"
  value       = aws_vpc.this.default_route_table_id
}

output "default_security_group_id" {
  description = "returns a string"
  value       = aws_vpc.this.default_security_group_id
}

output "dhcp_options_id" {
  description = "returns a string"
  value       = aws_vpc.this.dhcp_options_id
}

output "enable_classiclink" {
  description = "returns a bool"
  value       = aws_vpc.this.enable_classiclink
}

output "enable_classiclink_dns_support" {
  description = "returns a bool"
  value       = aws_vpc.this.enable_classiclink_dns_support
}

output "enable_dns_hostnames" {
  description = "returns a bool"
  value       = aws_vpc.this.enable_dns_hostnames
}

output "id" {
  description = "returns a string"
  value       = aws_vpc.this.id
}

output "ipv6_association_id" {
  description = "returns a string"
  value       = aws_vpc.this.ipv6_association_id
}

output "ipv6_cidr_block" {
  description = "returns a string"
  value       = aws_vpc.this.ipv6_cidr_block
}

output "main_route_table_id" {
  description = "returns a string"
  value       = aws_vpc.this.main_route_table_id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_vpc.this.owner_id
}

output "tags_all" {
  description = "returns a map of string"
  value       = aws_vpc.this.tags_all
}

output "this" {
  value = aws_vpc.this
}
```

[top](#index)