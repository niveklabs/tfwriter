# aws_api_gateway_method_response

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
module "aws_api_gateway_method_response" {
  source = "./modules/aws/r/aws_api_gateway_method_response"

  # http_method - (required) is a type of string
  http_method = null
  # resource_id - (required) is a type of string
  resource_id = null
  # response_models - (optional) is a type of map of string
  response_models = {}
  # response_parameters - (optional) is a type of map of bool
  response_parameters = {}
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # status_code - (required) is a type of string
  status_code = null
}
```

[top](#index)

### Variables

```terraform
variable "http_method" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "response_models" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "response_parameters" {
  description = "(optional)"
  type        = map(bool)
  default     = null
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "status_code" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_method_response" "this" {
  # http_method - (required) is a type of string
  http_method = var.http_method
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # response_models - (optional) is a type of map of string
  response_models = var.response_models
  # response_parameters - (optional) is a type of map of bool
  response_parameters = var.response_parameters
  # rest_api_id - (required) is a type of string
  rest_api_id = var.rest_api_id
  # status_code - (required) is a type of string
  status_code = var.status_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_method_response.this.id
}

output "this" {
  value = aws_api_gateway_method_response.this
}
```

[top](#index)