# aws_api_gateway_rest_api

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
module "aws_api_gateway_rest_api" {
  source = "./modules/aws/r/aws_api_gateway_rest_api"

  # api_key_source - (optional) is a type of string
  api_key_source = null
  # binary_media_types - (optional) is a type of list of string
  binary_media_types = []
  # body - (optional) is a type of string
  body = null
  # description - (optional) is a type of string
  description = null
  # disable_execute_api_endpoint - (optional) is a type of bool
  disable_execute_api_endpoint = null
  # minimum_compression_size - (optional) is a type of number
  minimum_compression_size = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # policy - (optional) is a type of string
  policy = null
  # tags - (optional) is a type of map of string
  tags = {}

  endpoint_configuration = [{
    types            = []
    vpc_endpoint_ids = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_key_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "binary_media_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "body" {
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

variable "minimum_compression_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "endpoint_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      types            = list(string)
      vpc_endpoint_ids = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_rest_api" "this" {
  # api_key_source - (optional) is a type of string
  api_key_source = var.api_key_source
  # binary_media_types - (optional) is a type of list of string
  binary_media_types = var.binary_media_types
  # body - (optional) is a type of string
  body = var.body
  # description - (optional) is a type of string
  description = var.description
  # disable_execute_api_endpoint - (optional) is a type of bool
  disable_execute_api_endpoint = var.disable_execute_api_endpoint
  # minimum_compression_size - (optional) is a type of number
  minimum_compression_size = var.minimum_compression_size
  # name - (required) is a type of string
  name = var.name
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # policy - (optional) is a type of string
  policy = var.policy
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "endpoint_configuration" {
    for_each = var.endpoint_configuration
    content {
      # types - (required) is a type of list of string
      types = endpoint_configuration.value["types"]
      # vpc_endpoint_ids - (optional) is a type of set of string
      vpc_endpoint_ids = endpoint_configuration.value["vpc_endpoint_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_key_source" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.api_key_source
}

output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.arn
}

output "binary_media_types" {
  description = "returns a list of string"
  value       = aws_api_gateway_rest_api.this.binary_media_types
}

output "created_date" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.created_date
}

output "description" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.description
}

output "disable_execute_api_endpoint" {
  description = "returns a bool"
  value       = aws_api_gateway_rest_api.this.disable_execute_api_endpoint
}

output "execution_arn" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.id
}

output "policy" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.policy
}

output "root_resource_id" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api.this.root_resource_id
}

output "this" {
  value = aws_api_gateway_rest_api.this
}
```

[top](#index)