# aws_network_acl

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_network_acl" {
  source = "./modules/aws/r/aws_network_acl"

  # egress - (optional) is a type of set of object
  egress = [{
    action          = null
    cidr_block      = null
    from_port       = null
    icmp_code       = null
    icmp_type       = null
    ipv6_cidr_block = null
    protocol        = null
    rule_no         = null
    to_port         = null
  }]
  # ingress - (optional) is a type of set of object
  ingress = [{
    action          = null
    cidr_block      = null
    from_port       = null
    icmp_code       = null
    icmp_type       = null
    ipv6_cidr_block = null
    protocol        = null
    rule_no         = null
    to_port         = null
  }]
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```hcl
variable "egress" {
  description = "(optional)"
  type = set(object(
    {
      action          = string
      cidr_block      = string
      from_port       = number
      icmp_code       = number
      icmp_type       = number
      ipv6_cidr_block = string
      protocol        = string
      rule_no         = number
      to_port         = number
    }
  ))
  default = null
}

variable "ingress" {
  description = "(optional)"
  type = set(object(
    {
      action          = string
      cidr_block      = string
      from_port       = number
      icmp_code       = number
      icmp_type       = number
      ipv6_cidr_block = string
      protocol        = string
      rule_no         = number
      to_port         = number
    }
  ))
  default = null
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

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_network_acl" "this" {
  egress     = var.egress
  ingress    = var.ingress
  subnet_ids = var.subnet_ids
  tags       = var.tags
  vpc_id     = var.vpc_id
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_network_acl.this.arn
}

output "egress" {
  description = "returns a set of object"
  value       = aws_network_acl.this.egress
}

output "id" {
  description = "returns a string"
  value       = aws_network_acl.this.id
}

output "ingress" {
  description = "returns a set of object"
  value       = aws_network_acl.this.ingress
}

output "owner_id" {
  description = "returns a string"
  value       = aws_network_acl.this.owner_id
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = aws_network_acl.this.subnet_ids
}

output "this" {
  value = aws_network_acl.this
}
```

[top](#index)