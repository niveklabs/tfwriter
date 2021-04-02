# aws_api_gateway_integration

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
module "aws_api_gateway_integration" {
  source = "./modules/aws/r/aws_api_gateway_integration"

  # cache_key_parameters - (optional) is a type of set of string
  cache_key_parameters = []
  # cache_namespace - (optional) is a type of string
  cache_namespace = null
  # connection_id - (optional) is a type of string
  connection_id = null
  # connection_type - (optional) is a type of string
  connection_type = null
  # content_handling - (optional) is a type of string
  content_handling = null
  # credentials - (optional) is a type of string
  credentials = null
  # http_method - (required) is a type of string
  http_method = null
  # integration_http_method - (optional) is a type of string
  integration_http_method = null
  # passthrough_behavior - (optional) is a type of string
  passthrough_behavior = null
  # request_parameters - (optional) is a type of map of string
  request_parameters = {}
  # request_templates - (optional) is a type of map of string
  request_templates = {}
  # resource_id - (required) is a type of string
  resource_id = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # timeout_milliseconds - (optional) is a type of number
  timeout_milliseconds = null
  # type - (required) is a type of string
  type = null
  # uri - (optional) is a type of string
  uri = null

  tls_config = [{
    insecure_skip_verification = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cache_key_parameters" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cache_namespace" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "content_handling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "credentials" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_method" {
  description = "(required)"
  type        = string
}

variable "integration_http_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passthrough_behavior" {
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

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "timeout_milliseconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tls_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      insecure_skip_verification = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_integration" "this" {
  cache_key_parameters    = var.cache_key_parameters
  cache_namespace         = var.cache_namespace
  connection_id           = var.connection_id
  connection_type         = var.connection_type
  content_handling        = var.content_handling
  credentials             = var.credentials
  http_method             = var.http_method
  integration_http_method = var.integration_http_method
  passthrough_behavior    = var.passthrough_behavior
  request_parameters      = var.request_parameters
  request_templates       = var.request_templates
  resource_id             = var.resource_id
  rest_api_id             = var.rest_api_id
  timeout_milliseconds    = var.timeout_milliseconds
  type                    = var.type
  uri                     = var.uri

  dynamic "tls_config" {
    for_each = var.tls_config
    content {
      insecure_skip_verification = tls_config.value["insecure_skip_verification"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cache_namespace" {
  description = "returns a string"
  value       = aws_api_gateway_integration.this.cache_namespace
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_integration.this.id
}

output "passthrough_behavior" {
  description = "returns a string"
  value       = aws_api_gateway_integration.this.passthrough_behavior
}

output "this" {
  value = aws_api_gateway_integration.this
}
```

[top](#index)