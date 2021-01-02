# aws_api_gateway_gateway_response

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_gateway_response" {
  source = "./modules/aws/r/aws_api_gateway_gateway_response"

  # response_parameters - (optional) is a type of map of string
  response_parameters = {}
  # response_templates - (optional) is a type of map of string
  response_templates = {}
  # response_type - (required) is a type of string
  response_type = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # status_code - (optional) is a type of string
  status_code = null
}
```

[top](#index)

### Variables

```terraform
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

variable "response_type" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "status_code" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_gateway_response" "this" {
  response_parameters = var.response_parameters
  response_templates  = var.response_templates
  response_type       = var.response_type
  rest_api_id         = var.rest_api_id
  status_code         = var.status_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_gateway_response.this.id
}

output "this" {
  value = aws_api_gateway_gateway_response.this
}
```

[top](#index)