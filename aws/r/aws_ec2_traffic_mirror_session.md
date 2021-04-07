# aws_ec2_traffic_mirror_session

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
module "aws_ec2_traffic_mirror_session" {
  source = "./modules/aws/r/aws_ec2_traffic_mirror_session"

  # description - (optional) is a type of string
  description = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null
  # packet_length - (optional) is a type of number
  packet_length = null
  # session_number - (required) is a type of number
  session_number = null
  # tags - (optional) is a type of map of string
  tags = {}
  # traffic_mirror_filter_id - (required) is a type of string
  traffic_mirror_filter_id = null
  # traffic_mirror_target_id - (required) is a type of string
  traffic_mirror_target_id = null
  # virtual_network_id - (optional) is a type of number
  virtual_network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_interface_id" {
  description = "(required)"
  type        = string
}

variable "packet_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_number" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "traffic_mirror_filter_id" {
  description = "(required)"
  type        = string
}

variable "traffic_mirror_target_id" {
  description = "(required)"
  type        = string
}

variable "virtual_network_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_traffic_mirror_session" "this" {
  # description - (optional) is a type of string
  description = var.description
  # network_interface_id - (required) is a type of string
  network_interface_id = var.network_interface_id
  # packet_length - (optional) is a type of number
  packet_length = var.packet_length
  # session_number - (required) is a type of number
  session_number = var.session_number
  # tags - (optional) is a type of map of string
  tags = var.tags
  # traffic_mirror_filter_id - (required) is a type of string
  traffic_mirror_filter_id = var.traffic_mirror_filter_id
  # traffic_mirror_target_id - (required) is a type of string
  traffic_mirror_target_id = var.traffic_mirror_target_id
  # virtual_network_id - (optional) is a type of number
  virtual_network_id = var.virtual_network_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_session.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_session.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_session.this.owner_id
}

output "virtual_network_id" {
  description = "returns a number"
  value       = aws_ec2_traffic_mirror_session.this.virtual_network_id
}

output "this" {
  value = aws_ec2_traffic_mirror_session.this
}
```

[top](#index)