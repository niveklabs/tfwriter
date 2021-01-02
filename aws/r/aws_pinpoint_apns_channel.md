# aws_pinpoint_apns_channel

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
module "aws_pinpoint_apns_channel" {
  source = "./modules/aws/r/aws_pinpoint_apns_channel"

  # application_id - (required) is a type of string
  application_id = null
  # bundle_id - (optional) is a type of string
  bundle_id = null
  # certificate - (optional) is a type of string
  certificate = null
  # default_authentication_method - (optional) is a type of string
  default_authentication_method = null
  # enabled - (optional) is a type of bool
  enabled = null
  # private_key - (optional) is a type of string
  private_key = null
  # team_id - (optional) is a type of string
  team_id = null
  # token_key - (optional) is a type of string
  token_key = null
  # token_key_id - (optional) is a type of string
  token_key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "bundle_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_authentication_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "team_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "token_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "token_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_pinpoint_apns_channel" "this" {
  application_id                = var.application_id
  bundle_id                     = var.bundle_id
  certificate                   = var.certificate
  default_authentication_method = var.default_authentication_method
  enabled                       = var.enabled
  private_key                   = var.private_key
  team_id                       = var.team_id
  token_key                     = var.token_key
  token_key_id                  = var.token_key_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_pinpoint_apns_channel.this.id
}

output "this" {
  value = aws_pinpoint_apns_channel.this
}
```

[top](#index)