# aws_ec2_traffic_mirror_filter_rule
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
module "aws_ec2_traffic_mirror_filter_rule" {
  source = "./modules/aws/r/aws_ec2_traffic_mirror_filter_rule"

  # description - (optional) is a type of string
  description = null
  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = null
  # protocol - (optional) is a type of number
  protocol = null
  # rule_action - (required) is a type of string
  rule_action = null
  # rule_number - (required) is a type of number
  rule_number = null
  # source_cidr_block - (required) is a type of string
  source_cidr_block = null
  # traffic_direction - (required) is a type of string
  traffic_direction = null
  # traffic_mirror_filter_id - (required) is a type of string
  traffic_mirror_filter_id = null

  destination_port_range = [{
    from_port = null
    to_port   = null
  }]

  source_port_range = [{
    from_port = null
    to_port   = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_cidr_block" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rule_action" {
  description = "(required)"
  type        = string
}

variable "rule_number" {
  description = "(required)"
  type        = number
}

variable "source_cidr_block" {
  description = "(required)"
  type        = string
}

variable "traffic_direction" {
  description = "(required)"
  type        = string
}

variable "traffic_mirror_filter_id" {
  description = "(required)"
  type        = string
}

variable "destination_port_range" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      from_port = number
      to_port   = number
    }
  ))
  default = []
}

variable "source_port_range" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      from_port = number
      to_port   = number
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_ec2_traffic_mirror_filter_rule" "this" {
  description              = var.description
  destination_cidr_block   = var.destination_cidr_block
  protocol                 = var.protocol
  rule_action              = var.rule_action
  rule_number              = var.rule_number
  source_cidr_block        = var.source_cidr_block
  traffic_direction        = var.traffic_direction
  traffic_mirror_filter_id = var.traffic_mirror_filter_id

  dynamic "destination_port_range" {
    for_each = var.destination_port_range
    content {
      from_port = destination_port_range.value["from_port"]
      to_port   = destination_port_range.value["to_port"]
    }
  }

  dynamic "source_port_range" {
    for_each = var.source_port_range
    content {
      from_port = source_port_range.value["from_port"]
      to_port   = source_port_range.value["to_port"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_filter_rule.this.id
}

output "this" {
  value = aws_ec2_traffic_mirror_filter_rule.this
}
```
[top](#index)
