# aws_autoscaling_notification

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
module "aws_autoscaling_notification" {
  source = "./modules/aws/r/aws_autoscaling_notification"

  # group_names - (required) is a type of set of string
  group_names = []
  # notifications - (required) is a type of set of string
  notifications = []
  # topic_arn - (required) is a type of string
  topic_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "group_names" {
  description = "(required)"
  type        = set(string)
}

variable "notifications" {
  description = "(required)"
  type        = set(string)
}

variable "topic_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_autoscaling_notification" "this" {
  # group_names - (required) is a type of set of string
  group_names = var.group_names
  # notifications - (required) is a type of set of string
  notifications = var.notifications
  # topic_arn - (required) is a type of string
  topic_arn = var.topic_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_autoscaling_notification.this.id
}

output "this" {
  value = aws_autoscaling_notification.this
}
```

[top](#index)