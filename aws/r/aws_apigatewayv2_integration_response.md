# aws_apigatewayv2_integration_response

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
module "aws_apigatewayv2_integration_response" {
  source = "./modules/aws/r/aws_apigatewayv2_integration_response"

  # api_id - (required) is a type of string
  api_id = null
  # content_handling_strategy - (optional) is a type of string
  content_handling_strategy = null
  # integration_id - (required) is a type of string
  integration_id = null
  # integration_response_key - (required) is a type of string
  integration_response_key = null
  # response_templates - (optional) is a type of map of string
  response_templates = {}
  # template_selection_expression - (optional) is a type of string
  template_selection_expression = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "content_handling_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integration_id" {
  description = "(required)"
  type        = string
}

variable "integration_response_key" {
  description = "(required)"
  type        = string
}

variable "response_templates" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_integration_response" "this" {
  api_id                        = var.api_id
  content_handling_strategy     = var.content_handling_strategy
  integration_id                = var.integration_id
  integration_response_key      = var.integration_response_key
  response_templates            = var.response_templates
  template_selection_expression = var.template_selection_expression
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_integration_response.this.id
}

output "this" {
  value = aws_apigatewayv2_integration_response.this
}
```

[top](#index)