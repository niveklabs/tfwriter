# aws_apigatewayv2_integration

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
module "aws_apigatewayv2_integration" {
  source = "./modules/aws/r/aws_apigatewayv2_integration"

  # api_id - (required) is a type of string
  api_id = null
  # connection_id - (optional) is a type of string
  connection_id = null
  # connection_type - (optional) is a type of string
  connection_type = null
  # content_handling_strategy - (optional) is a type of string
  content_handling_strategy = null
  # credentials_arn - (optional) is a type of string
  credentials_arn = null
  # description - (optional) is a type of string
  description = null
  # integration_method - (optional) is a type of string
  integration_method = null
  # integration_subtype - (optional) is a type of string
  integration_subtype = null
  # integration_type - (required) is a type of string
  integration_type = null
  # integration_uri - (optional) is a type of string
  integration_uri = null
  # passthrough_behavior - (optional) is a type of string
  passthrough_behavior = null
  # payload_format_version - (optional) is a type of string
  payload_format_version = null
  # request_parameters - (optional) is a type of map of string
  request_parameters = {}
  # request_templates - (optional) is a type of map of string
  request_templates = {}
  # template_selection_expression - (optional) is a type of string
  template_selection_expression = null
  # timeout_milliseconds - (optional) is a type of number
  timeout_milliseconds = null

  response_parameters = [{
    mappings    = {}
    status_code = null
  }]

  tls_config = [{
    server_name_to_verify = null
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

variable "connection_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_handling_strategy" {
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

variable "integration_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integration_subtype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integration_type" {
  description = "(required)"
  type        = string
}

variable "integration_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passthrough_behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payload_format_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "request_templates" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_selection_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout_milliseconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "response_parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      mappings    = map(string)
      status_code = string
    }
  ))
  default = []
}

variable "tls_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      server_name_to_verify = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_integration" "this" {
  # api_id - (required) is a type of string
  api_id = var.api_id
  # connection_id - (optional) is a type of string
  connection_id = var.connection_id
  # connection_type - (optional) is a type of string
  connection_type = var.connection_type
  # content_handling_strategy - (optional) is a type of string
  content_handling_strategy = var.content_handling_strategy
  # credentials_arn - (optional) is a type of string
  credentials_arn = var.credentials_arn
  # description - (optional) is a type of string
  description = var.description
  # integration_method - (optional) is a type of string
  integration_method = var.integration_method
  # integration_subtype - (optional) is a type of string
  integration_subtype = var.integration_subtype
  # integration_type - (required) is a type of string
  integration_type = var.integration_type
  # integration_uri - (optional) is a type of string
  integration_uri = var.integration_uri
  # passthrough_behavior - (optional) is a type of string
  passthrough_behavior = var.passthrough_behavior
  # payload_format_version - (optional) is a type of string
  payload_format_version = var.payload_format_version
  # request_parameters - (optional) is a type of map of string
  request_parameters = var.request_parameters
  # request_templates - (optional) is a type of map of string
  request_templates = var.request_templates
  # template_selection_expression - (optional) is a type of string
  template_selection_expression = var.template_selection_expression
  # timeout_milliseconds - (optional) is a type of number
  timeout_milliseconds = var.timeout_milliseconds

  dynamic "response_parameters" {
    for_each = var.response_parameters
    content {
      # mappings - (required) is a type of map of string
      mappings = response_parameters.value["mappings"]
      # status_code - (required) is a type of string
      status_code = response_parameters.value["status_code"]
    }
  }

  dynamic "tls_config" {
    for_each = var.tls_config
    content {
      # server_name_to_verify - (optional) is a type of string
      server_name_to_verify = tls_config.value["server_name_to_verify"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_integration.this.id
}

output "integration_response_selection_expression" {
  description = "returns a string"
  value       = aws_apigatewayv2_integration.this.integration_response_selection_expression
}

output "timeout_milliseconds" {
  description = "returns a number"
  value       = aws_apigatewayv2_integration.this.timeout_milliseconds
}

output "this" {
  value = aws_apigatewayv2_integration.this
}
```

[top](#index)