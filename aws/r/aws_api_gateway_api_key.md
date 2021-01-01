# aws_api_gateway_api_key

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_api_gateway_api_key" {
  source = "./modules/aws/r/aws_api_gateway_api_key"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_api_gateway_api_key" "this" {
  description = var.description
  enabled     = var.enabled
  name        = var.name
  tags        = var.tags
  value       = var.value
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_api_key.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_api_gateway_api_key.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_api_key.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_api_gateway_api_key.this.last_updated_date
}

output "value" {
  description = "returns a string"
  value       = aws_api_gateway_api_key.this.value
  sensitive   = true
}

output "this" {
  value = aws_api_gateway_api_key.this
}
```

[top](#index)