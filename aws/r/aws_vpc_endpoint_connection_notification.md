# aws_vpc_endpoint_connection_notification

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
module "aws_vpc_endpoint_connection_notification" {
  source = "./modules/aws/r/aws_vpc_endpoint_connection_notification"

  # connection_events - (required) is a type of set of string
  connection_events = []
  # connection_notification_arn - (required) is a type of string
  connection_notification_arn = null
  # vpc_endpoint_id - (optional) is a type of string
  vpc_endpoint_id = null
  # vpc_endpoint_service_id - (optional) is a type of string
  vpc_endpoint_service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_events" {
  description = "(required)"
  type        = set(string)
}

variable "connection_notification_arn" {
  description = "(required)"
  type        = string
}

variable "vpc_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_endpoint_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc_endpoint_connection_notification" "this" {
  # connection_events - (required) is a type of set of string
  connection_events = var.connection_events
  # connection_notification_arn - (required) is a type of string
  connection_notification_arn = var.connection_notification_arn
  # vpc_endpoint_id - (optional) is a type of string
  vpc_endpoint_id = var.vpc_endpoint_id
  # vpc_endpoint_service_id - (optional) is a type of string
  vpc_endpoint_service_id = var.vpc_endpoint_service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_vpc_endpoint_connection_notification.this.id
}

output "notification_type" {
  description = "returns a string"
  value       = aws_vpc_endpoint_connection_notification.this.notification_type
}

output "state" {
  description = "returns a string"
  value       = aws_vpc_endpoint_connection_notification.this.state
}

output "this" {
  value = aws_vpc_endpoint_connection_notification.this
}
```

[top](#index)