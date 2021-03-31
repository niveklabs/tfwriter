# aws_api_gateway_integration_response

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
module "aws_api_gateway_integration_response" {
  source = "./modules/aws/r/aws_api_gateway_integration_response"

  # content_handling - (optional) is a type of string
  content_handling = null
  # http_method - (required) is a type of string
  http_method = null
  # resource_id - (required) is a type of string
  resource_id = null
  # response_parameters - (optional) is a type of map of string
  response_parameters = {}
  # response_templates - (optional) is a type of map of string
  response_templates = {}
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # selection_pattern - (optional) is a type of string
  selection_pattern = null
  # status_code - (required) is a type of string
  status_code = null
}
```

[top](#index)

### Variables

```terraform
variable "content_handling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_method" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "response_parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "response_templates" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "selection_pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status_code" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_integration_response" "this" {
  content_handling    = var.content_handling
  http_method         = var.http_method
  resource_id         = var.resource_id
  response_parameters = var.response_parameters
  response_templates  = var.response_templates
  rest_api_id         = var.rest_api_id
  selection_pattern   = var.selection_pattern
  status_code         = var.status_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_integration_response.this.id
}

output "this" {
  value = aws_api_gateway_integration_response.this
}
```

[top](#index)