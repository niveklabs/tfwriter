# aws_api_gateway_method

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_method" {
  source = "./modules/aws/r/aws_api_gateway_method"

  # api_key_required - (optional) is a type of bool
  api_key_required = null
  # authorization - (required) is a type of string
  authorization = null
  # authorization_scopes - (optional) is a type of set of string
  authorization_scopes = []
  # authorizer_id - (optional) is a type of string
  authorizer_id = null
  # http_method - (required) is a type of string
  http_method = null
  # operation_name - (optional) is a type of string
  operation_name = null
  # request_models - (optional) is a type of map of string
  request_models = {}
  # request_parameters - (optional) is a type of map of bool
  request_parameters = {}
  # request_validator_id - (optional) is a type of string
  request_validator_id = null
  # resource_id - (required) is a type of string
  resource_id = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "authorization" {
  description = "(required)"
  type        = string
}

variable "authorization_scopes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "authorizer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_method" {
  description = "(required)"
  type        = string
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

variable "request_parameters" {
  description = "(optional)"
  type        = map(bool)
  default     = null
}

variable "request_validator_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_method" "this" {
  api_key_required     = var.api_key_required
  authorization        = var.authorization
  authorization_scopes = var.authorization_scopes
  authorizer_id        = var.authorizer_id
  http_method          = var.http_method
  operation_name       = var.operation_name
  request_models       = var.request_models
  request_parameters   = var.request_parameters
  request_validator_id = var.request_validator_id
  resource_id          = var.resource_id
  rest_api_id          = var.rest_api_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_method.this.id
}

output "this" {
  value = aws_api_gateway_method.this
}
```

[top](#index)