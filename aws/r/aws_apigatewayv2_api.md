# aws_apigatewayv2_api

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
module "aws_apigatewayv2_api" {
  source = "./modules/aws/r/aws_apigatewayv2_api"

  # api_key_selection_expression - (optional) is a type of string
  api_key_selection_expression = null
  # body - (optional) is a type of string
  body = null
  # credentials_arn - (optional) is a type of string
  credentials_arn = null
  # description - (optional) is a type of string
  description = null
  # disable_execute_api_endpoint - (optional) is a type of bool
  disable_execute_api_endpoint = null
  # fail_on_warnings - (optional) is a type of bool
  fail_on_warnings = null
  # name - (required) is a type of string
  name = null
  # protocol_type - (required) is a type of string
  protocol_type = null
  # route_key - (optional) is a type of string
  route_key = null
  # route_selection_expression - (optional) is a type of string
  route_selection_expression = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target - (optional) is a type of string
  target = null
  # version - (optional) is a type of string
  version = null

  cors_configuration = [{
    allow_credentials = null
    allow_headers     = []
    allow_methods     = []
    allow_origins     = []
    expose_headers    = []
    max_age           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_key_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "credentials_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_execute_api_endpoint" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fail_on_warnings" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol_type" {
  description = "(required)"
  type        = string
}

variable "route_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cors_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_credentials = bool
      allow_headers     = set(string)
      allow_methods     = set(string)
      allow_origins     = set(string)
      expose_headers    = set(string)
      max_age           = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_api" "this" {
  # api_key_selection_expression - (optional) is a type of string
  api_key_selection_expression = var.api_key_selection_expression
  # body - (optional) is a type of string
  body = var.body
  # credentials_arn - (optional) is a type of string
  credentials_arn = var.credentials_arn
  # description - (optional) is a type of string
  description = var.description
  # disable_execute_api_endpoint - (optional) is a type of bool
  disable_execute_api_endpoint = var.disable_execute_api_endpoint
  # fail_on_warnings - (optional) is a type of bool
  fail_on_warnings = var.fail_on_warnings
  # name - (required) is a type of string
  name = var.name
  # protocol_type - (required) is a type of string
  protocol_type = var.protocol_type
  # route_key - (optional) is a type of string
  route_key = var.route_key
  # route_selection_expression - (optional) is a type of string
  route_selection_expression = var.route_selection_expression
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target - (optional) is a type of string
  target = var.target
  # version - (optional) is a type of string
  version = var.version

  dynamic "cors_configuration" {
    for_each = var.cors_configuration
    content {
      # allow_credentials - (optional) is a type of bool
      allow_credentials = cors_configuration.value["allow_credentials"]
      # allow_headers - (optional) is a type of set of string
      allow_headers = cors_configuration.value["allow_headers"]
      # allow_methods - (optional) is a type of set of string
      allow_methods = cors_configuration.value["allow_methods"]
      # allow_origins - (optional) is a type of set of string
      allow_origins = cors_configuration.value["allow_origins"]
      # expose_headers - (optional) is a type of set of string
      expose_headers = cors_configuration.value["expose_headers"]
      # max_age - (optional) is a type of number
      max_age = cors_configuration.value["max_age"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_endpoint" {
  description = "returns a string"
  value       = aws_apigatewayv2_api.this.api_endpoint
}

output "arn" {
  description = "returns a string"
  value       = aws_apigatewayv2_api.this.arn
}

output "execution_arn" {
  description = "returns a string"
  value       = aws_apigatewayv2_api.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_api.this.id
}

output "this" {
  value = aws_apigatewayv2_api.this
}
```

[top](#index)