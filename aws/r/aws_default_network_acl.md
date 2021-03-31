# aws_default_network_acl

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_default_network_acl" {
  source = "./modules/aws/r/aws_default_network_acl"

  # default_network_acl_id - (required) is a type of string
  default_network_acl_id = null
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

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
}
```

[top](#index)

### Variables

```terraform
variable "default_network_acl_id" {
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

variable "egress" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
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
  default = []
}

variable "ingress" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
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
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_default_network_acl" "this" {
  default_network_acl_id = var.default_network_acl_id
  subnet_ids             = var.subnet_ids
  tags                   = var.tags

  dynamic "egress" {
    for_each = var.egress
    content {
      action          = egress.value["action"]
      cidr_block      = egress.value["cidr_block"]
      from_port       = egress.value["from_port"]
      icmp_code       = egress.value["icmp_code"]
      icmp_type       = egress.value["icmp_type"]
      ipv6_cidr_block = egress.value["ipv6_cidr_block"]
      protocol        = egress.value["protocol"]
      rule_no         = egress.value["rule_no"]
      to_port         = egress.value["to_port"]
    }
  }

  dynamic "ingress" {
    for_each = var.ingress
    content {
      action          = ingress.value["action"]
      cidr_block      = ingress.value["cidr_block"]
      from_port       = ingress.value["from_port"]
      icmp_code       = ingress.value["icmp_code"]
      icmp_type       = ingress.value["icmp_type"]
      ipv6_cidr_block = ingress.value["ipv6_cidr_block"]
      protocol        = ingress.value["protocol"]
      rule_no         = ingress.value["rule_no"]
      to_port         = ingress.value["to_port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_default_network_acl.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_default_network_acl.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_default_network_acl.this.owner_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_default_network_acl.this.vpc_id
}

output "this" {
  value = aws_default_network_acl.this
}
```

[top](#index)