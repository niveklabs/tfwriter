# aws_network_acl_rule

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_network_acl_rule" {
  source = "./modules/aws/r/aws_network_acl_rule"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # egress - (optional) is a type of bool
  egress = null
  # from_port - (optional) is a type of number
  from_port = null
  # icmp_code - (optional) is a type of string
  icmp_code = null
  # icmp_type - (optional) is a type of string
  icmp_type = null
  # ipv6_cidr_block - (optional) is a type of string
  ipv6_cidr_block = null
  # network_acl_id - (required) is a type of string
  network_acl_id = null
  # protocol - (required) is a type of string
  protocol = null
  # rule_action - (required) is a type of string
  rule_action = null
  # rule_number - (required) is a type of number
  rule_number = null
  # to_port - (optional) is a type of number
  to_port = null
}
```

[top](#index)

### Variables

```hcl
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "egress" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "from_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmp_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_acl_id" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "rule_action" {
  description = "(required)"
  type        = string
}

variable "rule_number" {
  description = "(required)"
  type        = number
}

variable "to_port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_network_acl_rule" "this" {
  cidr_block      = var.cidr_block
  egress          = var.egress
  from_port       = var.from_port
  icmp_code       = var.icmp_code
  icmp_type       = var.icmp_type
  ipv6_cidr_block = var.ipv6_cidr_block
  network_acl_id  = var.network_acl_id
  protocol        = var.protocol
  rule_action     = var.rule_action
  rule_number     = var.rule_number
  to_port         = var.to_port
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_network_acl_rule.this.id
}

output "this" {
  value = aws_network_acl_rule.this
}
```

[top](#index)