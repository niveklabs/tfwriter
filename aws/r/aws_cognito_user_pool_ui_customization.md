# aws_cognito_user_pool_ui_customization

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
module "aws_cognito_user_pool_ui_customization" {
  source = "./modules/aws/r/aws_cognito_user_pool_ui_customization"

  # client_id - (optional) is a type of string
  client_id = null
  # css - (optional) is a type of string
  css = null
  # image_file - (optional) is a type of string
  image_file = null
  # user_pool_id - (required) is a type of string
  user_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "css" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_pool_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cognito_user_pool_ui_customization" "this" {
  client_id    = var.client_id
  css          = var.css
  image_file   = var.image_file
  user_pool_id = var.user_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = aws_cognito_user_pool_ui_customization.this.creation_date
}

output "css_version" {
  description = "returns a string"
  value       = aws_cognito_user_pool_ui_customization.this.css_version
}

output "id" {
  description = "returns a string"
  value       = aws_cognito_user_pool_ui_customization.this.id
}

output "image_url" {
  description = "returns a string"
  value       = aws_cognito_user_pool_ui_customization.this.image_url
}

output "last_modified_date" {
  description = "returns a string"
  value       = aws_cognito_user_pool_ui_customization.this.last_modified_date
}

output "this" {
  value = aws_cognito_user_pool_ui_customization.this
}
```

[top](#index)