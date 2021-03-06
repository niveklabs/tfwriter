# aws_ec2_traffic_mirror_target

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
module "aws_ec2_traffic_mirror_target" {
  source = "./modules/aws/r/aws_ec2_traffic_mirror_target"

  # description - (optional) is a type of string
  description = null
  # network_interface_id - (optional) is a type of string
  network_interface_id = null
  # network_load_balancer_arn - (optional) is a type of string
  network_load_balancer_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_load_balancer_arn" {
  description = "(optional)"
  type        = string
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
resource "aws_ec2_traffic_mirror_target" "this" {
  # description - (optional) is a type of string
  description = var.description
  # network_interface_id - (optional) is a type of string
  network_interface_id = var.network_interface_id
  # network_load_balancer_arn - (optional) is a type of string
  network_load_balancer_arn = var.network_load_balancer_arn
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_target.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_target.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_target.this.owner_id
}

output "this" {
  value = aws_ec2_traffic_mirror_target.this
}
```

[top](#index)