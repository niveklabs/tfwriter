# aws_api_gateway_usage_plan_key

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
module "aws_api_gateway_usage_plan_key" {
  source = "./modules/aws/r/aws_api_gateway_usage_plan_key"

  # key_id - (required) is a type of string
  key_id = null
  # key_type - (required) is a type of string
  key_type = null
  # usage_plan_id - (required) is a type of string
  usage_plan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "key_id" {
  description = "(required)"
  type        = string
}

variable "key_type" {
  description = "(required)"
  type        = string
}

variable "usage_plan_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_usage_plan_key" "this" {
  key_id        = var.key_id
  key_type      = var.key_type
  usage_plan_id = var.usage_plan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_usage_plan_key.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_api_gateway_usage_plan_key.this.name
}

output "value" {
  description = "returns a string"
  value       = aws_api_gateway_usage_plan_key.this.value
}

output "this" {
  value = aws_api_gateway_usage_plan_key.this
}
```

[top](#index)