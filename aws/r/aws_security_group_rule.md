# aws_security_group_rule
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
module "aws_security_group_rule" {
  source = "./modules/aws/r/aws_security_group_rule"

  # cidr_blocks - (optional) is a type of list of string
  cidr_blocks = []
  # description - (optional) is a type of string
  description = null
  # from_port - (required) is a type of number
  from_port = null
  # ipv6_cidr_blocks - (optional) is a type of list of string
  ipv6_cidr_blocks = []
  # prefix_list_ids - (optional) is a type of list of string
  prefix_list_ids = []
  # protocol - (required) is a type of string
  protocol = null
  # security_group_id - (required) is a type of string
  security_group_id = null
  # self - (optional) is a type of bool
  self = null
  # source_security_group_id - (optional) is a type of string
  source_security_group_id = null
  # to_port - (required) is a type of number
  to_port = null
  # type - (required) is a type of string
  type = null
}
```
[top](#index)
### Variables
```hcl
variable "cidr_blocks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "from_port" {
  description = "(required)"
  type        = number
}

variable "ipv6_cidr_blocks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "prefix_list_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "security_group_id" {
  description = "(required)"
  type        = string
}

variable "self" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "source_security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to_port" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(required) - Type of rule, ingress (inbound) or egress (outbound)."
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_security_group_rule" "this" {
  cidr_blocks              = var.cidr_blocks
  description              = var.description
  from_port                = var.from_port
  ipv6_cidr_blocks         = var.ipv6_cidr_blocks
  prefix_list_ids          = var.prefix_list_ids
  protocol                 = var.protocol
  security_group_id        = var.security_group_id
  self                     = var.self
  source_security_group_id = var.source_security_group_id
  to_port                  = var.to_port
  type                     = var.type
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_security_group_rule.this.id
}

output "source_security_group_id" {
  description = "returns a string"
  value       = aws_security_group_rule.this.source_security_group_id
}

output "this" {
  value = aws_security_group_rule.this
}
```
[top](#index)
