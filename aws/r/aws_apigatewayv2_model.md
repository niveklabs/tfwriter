# aws_apigatewayv2_model

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
module "aws_apigatewayv2_model" {
  source = "./modules/aws/r/aws_apigatewayv2_model"

  # api_id - (required) is a type of string
  api_id = null
  # content_type - (required) is a type of string
  content_type = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # schema - (required) is a type of string
  schema = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "content_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_model" "this" {
  api_id       = var.api_id
  content_type = var.content_type
  description  = var.description
  name         = var.name
  schema       = var.schema
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_model.this.id
}

output "this" {
  value = aws_apigatewayv2_model.this
}
```

[top](#index)