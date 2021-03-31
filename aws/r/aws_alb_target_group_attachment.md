# aws_alb_target_group_attachment

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
module "aws_alb_target_group_attachment" {
  source = "./modules/aws/r/aws_alb_target_group_attachment"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # port - (optional) is a type of number
  port = null
  # target_group_arn - (required) is a type of string
  target_group_arn = null
  # target_id - (required) is a type of string
  target_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "target_group_arn" {
  description = "(required)"
  type        = string
}

variable "target_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_alb_target_group_attachment" "this" {
  availability_zone = var.availability_zone
  port              = var.port
  target_group_arn  = var.target_group_arn
  target_id         = var.target_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_alb_target_group_attachment.this.id
}

output "this" {
  value = aws_alb_target_group_attachment.this
}
```

[top](#index)