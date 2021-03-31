# aws_pinpoint_gcm_channel

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
module "aws_pinpoint_gcm_channel" {
  source = "./modules/aws/r/aws_pinpoint_gcm_channel"

  # api_key - (required) is a type of string
  api_key = null
  # application_id - (required) is a type of string
  application_id = null
  # enabled - (optional) is a type of bool
  enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key" {
  description = "(required)"
  type        = string
}

variable "application_id" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_pinpoint_gcm_channel" "this" {
  api_key        = var.api_key
  application_id = var.application_id
  enabled        = var.enabled
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_pinpoint_gcm_channel.this.id
}

output "this" {
  value = aws_pinpoint_gcm_channel.this
}
```

[top](#index)