# aws_autoscaling_attachment

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
module "aws_autoscaling_attachment" {
  source = "./modules/aws/r/aws_autoscaling_attachment"

  # alb_target_group_arn - (optional) is a type of string
  alb_target_group_arn = null
  # autoscaling_group_name - (required) is a type of string
  autoscaling_group_name = null
  # elb - (optional) is a type of string
  elb = null
}
```

[top](#index)

### Variables

```terraform
variable "alb_target_group_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscaling_group_name" {
  description = "(required)"
  type        = string
}

variable "elb" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_autoscaling_attachment" "this" {
  alb_target_group_arn   = var.alb_target_group_arn
  autoscaling_group_name = var.autoscaling_group_name
  elb                    = var.elb
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_autoscaling_attachment.this.id
}

output "this" {
  value = aws_autoscaling_attachment.this
}
```

[top](#index)