# aws_appsync_api_key

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
module "aws_appsync_api_key" {
  source = "./modules/aws/r/aws_appsync_api_key"

  # api_id - (required) is a type of string
  api_id = null
  # description - (optional) is a type of string
  description = null
  # expires - (optional) is a type of string
  expires = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expires" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_appsync_api_key" "this" {
  api_id      = var.api_id
  description = var.description
  expires     = var.expires
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_appsync_api_key.this.id
}

output "key" {
  description = "returns a string"
  value       = aws_appsync_api_key.this.key
  sensitive   = true
}

output "this" {
  value = aws_appsync_api_key.this
}
```

[top](#index)