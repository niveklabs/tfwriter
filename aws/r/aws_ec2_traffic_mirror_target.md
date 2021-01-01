# aws_ec2_traffic_mirror_target

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

```hcl
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

```hcl
resource "aws_ec2_traffic_mirror_target" "this" {
  description               = var.description
  network_interface_id      = var.network_interface_id
  network_load_balancer_arn = var.network_load_balancer_arn
  tags                      = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_target.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_traffic_mirror_target.this.id
}

output "this" {
  value = aws_ec2_traffic_mirror_target.this
}
```

[top](#index)