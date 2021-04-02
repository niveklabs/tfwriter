# aws_api_gateway_rest_api

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_rest_api" {
  source = "./modules/aws/d/aws_api_gateway_rest_api"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "aws_api_gateway_rest_api" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "api_key_source" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.api_key_source
}

output "arn" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.arn
}

output "binary_media_types" {
  description = "returns a list of string"
  value       = data.aws_api_gateway_rest_api.this.binary_media_types
}

output "description" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.description
}

output "endpoint_configuration" {
  description = "returns a list of object"
  value       = data.aws_api_gateway_rest_api.this.endpoint_configuration
}

output "execution_arn" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.id
}

output "minimum_compression_size" {
  description = "returns a number"
  value       = data.aws_api_gateway_rest_api.this.minimum_compression_size
}

output "policy" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.policy
}

output "root_resource_id" {
  description = "returns a string"
  value       = data.aws_api_gateway_rest_api.this.root_resource_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_api_gateway_rest_api.this.tags
}

output "this" {
  value = aws_api_gateway_rest_api.this
}
```

[top](#index)