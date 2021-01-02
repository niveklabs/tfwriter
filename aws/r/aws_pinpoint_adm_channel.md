# aws_pinpoint_adm_channel

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_pinpoint_adm_channel" {
  source = "./modules/aws/r/aws_pinpoint_adm_channel"

  # application_id - (required) is a type of string
  application_id = null
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # enabled - (optional) is a type of bool
  enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
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
resource "aws_pinpoint_adm_channel" "this" {
  application_id = var.application_id
  client_id      = var.client_id
  client_secret  = var.client_secret
  enabled        = var.enabled
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_pinpoint_adm_channel.this.id
}

output "this" {
  value = aws_pinpoint_adm_channel.this
}
```

[top](#index)