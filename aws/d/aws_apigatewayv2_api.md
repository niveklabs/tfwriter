# aws_apigatewayv2_api

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_apigatewayv2_api" {
  source = "./modules/aws/d/aws_apigatewayv2_api"

  # api_id - (required) is a type of string
  api_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_apigatewayv2_api" "this" {
  api_id = var.api_id
  tags   = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "api_endpoint" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.api_endpoint
}

output "api_key_selection_expression" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.api_key_selection_expression
}

output "arn" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.arn
}

output "cors_configuration" {
  description = "returns a list of object"
  value       = data.aws_apigatewayv2_api.this.cors_configuration
}

output "description" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.description
}

output "disable_execute_api_endpoint" {
  description = "returns a bool"
  value       = data.aws_apigatewayv2_api.this.disable_execute_api_endpoint
}

output "execution_arn" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.name
}

output "protocol_type" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.protocol_type
}

output "route_selection_expression" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.route_selection_expression
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_apigatewayv2_api.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_api.this.version
}

output "this" {
  value = aws_apigatewayv2_api.this
}
```

[top](#index)