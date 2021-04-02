# aws_dx_connection

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
module "aws_dx_connection" {
  source = "./modules/aws/r/aws_dx_connection"

  # bandwidth - (required) is a type of string
  bandwidth = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "aws_dx_connection" "this" {
  bandwidth = var.bandwidth
  location  = var.location
  name      = var.name
  tags      = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_dx_connection.this.arn
}

output "aws_device" {
  description = "returns a string"
  value       = aws_dx_connection.this.aws_device
}

output "has_logical_redundancy" {
  description = "returns a string"
  value       = aws_dx_connection.this.has_logical_redundancy
}

output "id" {
  description = "returns a string"
  value       = aws_dx_connection.this.id
}

output "jumbo_frame_capable" {
  description = "returns a bool"
  value       = aws_dx_connection.this.jumbo_frame_capable
}

output "this" {
  value = aws_dx_connection.this
}
```

[top](#index)