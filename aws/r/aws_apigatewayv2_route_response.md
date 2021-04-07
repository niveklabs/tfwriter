# aws_apigatewayv2_route_response

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
module "aws_apigatewayv2_route_response" {
  source = "./modules/aws/r/aws_apigatewayv2_route_response"

  # api_id - (required) is a type of string
  api_id = null
  # model_selection_expression - (optional) is a type of string
  model_selection_expression = null
  # response_models - (optional) is a type of map of string
  response_models = {}
  # route_id - (required) is a type of string
  route_id = null
  # route_response_key - (required) is a type of string
  route_response_key = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "model_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "response_models" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "route_id" {
  description = "(required)"
  type        = string
}

variable "route_response_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_route_response" "this" {
  # api_id - (required) is a type of string
  api_id = var.api_id
  # model_selection_expression - (optional) is a type of string
  model_selection_expression = var.model_selection_expression
  # response_models - (optional) is a type of map of string
  response_models = var.response_models
  # route_id - (required) is a type of string
  route_id = var.route_id
  # route_response_key - (required) is a type of string
  route_response_key = var.route_response_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_route_response.this.id
}

output "this" {
  value = aws_apigatewayv2_route_response.this
}
```

[top](#index)