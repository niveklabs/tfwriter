# aws_apigatewayv2_route

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
module "aws_apigatewayv2_route" {
  source = "./modules/aws/r/aws_apigatewayv2_route"

  # api_id - (required) is a type of string
  api_id = null
  # api_key_required - (optional) is a type of bool
  api_key_required = null
  # authorization_scopes - (optional) is a type of set of string
  authorization_scopes = []
  # authorization_type - (optional) is a type of string
  authorization_type = null
  # authorizer_id - (optional) is a type of string
  authorizer_id = null
  # model_selection_expression - (optional) is a type of string
  model_selection_expression = null
  # operation_name - (optional) is a type of string
  operation_name = null
  # request_models - (optional) is a type of map of string
  request_models = {}
  # route_key - (required) is a type of string
  route_key = null
  # route_response_selection_expression - (optional) is a type of string
  route_response_selection_expression = null
  # target - (optional) is a type of string
  target = null

  request_parameter = [{
    request_parameter_key = null
    required              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "api_key_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "authorization_scopes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "authorization_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorizer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "model_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operation_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_models" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "route_key" {
  description = "(required)"
  type        = string
}

variable "route_response_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_parameter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      request_parameter_key = string
      required              = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_route" "this" {
  # api_id - (required) is a type of string
  api_id = var.api_id
  # api_key_required - (optional) is a type of bool
  api_key_required = var.api_key_required
  # authorization_scopes - (optional) is a type of set of string
  authorization_scopes = var.authorization_scopes
  # authorization_type - (optional) is a type of string
  authorization_type = var.authorization_type
  # authorizer_id - (optional) is a type of string
  authorizer_id = var.authorizer_id
  # model_selection_expression - (optional) is a type of string
  model_selection_expression = var.model_selection_expression
  # operation_name - (optional) is a type of string
  operation_name = var.operation_name
  # request_models - (optional) is a type of map of string
  request_models = var.request_models
  # route_key - (required) is a type of string
  route_key = var.route_key
  # route_response_selection_expression - (optional) is a type of string
  route_response_selection_expression = var.route_response_selection_expression
  # target - (optional) is a type of string
  target = var.target

  dynamic "request_parameter" {
    for_each = var.request_parameter
    content {
      # request_parameter_key - (required) is a type of string
      request_parameter_key = request_parameter.value["request_parameter_key"]
      # required - (required) is a type of bool
      required = request_parameter.value["required"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_route.this.id
}

output "this" {
  value = aws_apigatewayv2_route.this
}
```

[top](#index)