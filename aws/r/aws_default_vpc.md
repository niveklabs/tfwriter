# aws_default_vpc

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
module "aws_default_vpc" {
  source = "./modules/aws/r/aws_default_vpc"

  # enable_classiclink - (optional) is a type of bool
  enable_classiclink = null
  # enable_classiclink_dns_support - (optional) is a type of bool
  enable_classiclink_dns_support = null
  # enable_dns_hostnames - (optional) is a type of bool
  enable_dns_hostnames = null
  # enable_dns_support - (optional) is a type of bool
  enable_dns_support = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_default_vpc" "this" {
  enable_classiclink             = var.enable_classiclink
  enable_classiclink_dns_support = var.enable_classiclink_dns_support
  enable_dns_hostnames           = var.enable_dns_hostnames
  enable_dns_support             = var.enable_dns_support
  tags                           = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_default_vpc.this.arn
}

output "assign_generated_ipv6_cidr_block" {
  description = "returns a bool"
  value       = aws_default_vpc.this.assign_generated_ipv6_cidr_block
}

output "cidr_block" {
  description = "returns a string"
  value       = aws_default_vpc.this.cidr_block
}

output "default_network_acl_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.default_network_acl_id
}

output "default_route_table_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.default_route_table_id
}

output "default_security_group_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.default_security_group_id
}

output "dhcp_options_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.dhcp_options_id
}

output "enable_classiclink" {
  description = "returns a bool"
  value       = aws_default_vpc.this.enable_classiclink
}

output "enable_classiclink_dns_support" {
  description = "returns a bool"
  value       = aws_default_vpc.this.enable_classiclink_dns_support
}

output "enable_dns_hostnames" {
  description = "returns a bool"
  value       = aws_default_vpc.this.enable_dns_hostnames
}

output "id" {
  description = "returns a string"
  value       = aws_default_vpc.this.id
}

output "instance_tenancy" {
  description = "returns a string"
  value       = aws_default_vpc.this.instance_tenancy
}

output "ipv6_association_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.ipv6_association_id
}

output "ipv6_cidr_block" {
  description = "returns a string"
  value       = aws_default_vpc.this.ipv6_cidr_block
}

output "main_route_table_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.main_route_table_id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_default_vpc.this.owner_id
}

output "this" {
  value = aws_default_vpc.this
}
```

[top](#index)