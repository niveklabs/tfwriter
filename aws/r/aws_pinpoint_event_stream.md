# aws_pinpoint_event_stream

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
module "aws_pinpoint_event_stream" {
  source = "./modules/aws/r/aws_pinpoint_event_stream"

  # application_id - (required) is a type of string
  application_id = null
  # destination_stream_arn - (required) is a type of string
  destination_stream_arn = null
  # role_arn - (required) is a type of string
  role_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "destination_stream_arn" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_pinpoint_event_stream" "this" {
  # application_id - (required) is a type of string
  application_id = var.application_id
  # destination_stream_arn - (required) is a type of string
  destination_stream_arn = var.destination_stream_arn
  # role_arn - (required) is a type of string
  role_arn = var.role_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_pinpoint_event_stream.this.id
}

output "this" {
  value = aws_pinpoint_event_stream.this
}
```

[top](#index)