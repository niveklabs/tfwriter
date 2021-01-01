# aws_apigatewayv2_authorizer
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_apigatewayv2_authorizer" {
  source = "./modules/aws/r/aws_apigatewayv2_authorizer"

  # api_id - (required) is a type of string
  api_id = null
  # authorizer_credentials_arn - (optional) is a type of string
  authorizer_credentials_arn = null
  # authorizer_payload_format_version - (optional) is a type of string
  authorizer_payload_format_version = null
  # authorizer_result_ttl_in_seconds - (optional) is a type of number
  authorizer_result_ttl_in_seconds = null
  # authorizer_type - (required) is a type of string
  authorizer_type = null
  # authorizer_uri - (optional) is a type of string
  authorizer_uri = null
  # enable_simple_responses - (optional) is a type of bool
  enable_simple_responses = null
  # identity_sources - (optional) is a type of set of string
  identity_sources = []
  # name - (required) is a type of string
  name = null

  jwt_configuration = [{
    audience = []
    issuer   = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "authorizer_credentials_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorizer_payload_format_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorizer_result_ttl_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authorizer_type" {
  description = "(required)"
  type        = string
}

variable "authorizer_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_simple_responses" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identity_sources" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "jwt_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audience = set(string)
      issuer   = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_apigatewayv2_authorizer" "this" {
  api_id                            = var.api_id
  authorizer_credentials_arn        = var.authorizer_credentials_arn
  authorizer_payload_format_version = var.authorizer_payload_format_version
  authorizer_result_ttl_in_seconds  = var.authorizer_result_ttl_in_seconds
  authorizer_type                   = var.authorizer_type
  authorizer_uri                    = var.authorizer_uri
  enable_simple_responses           = var.enable_simple_responses
  identity_sources                  = var.identity_sources
  name                              = var.name

  dynamic "jwt_configuration" {
    for_each = var.jwt_configuration
    content {
      audience = jwt_configuration.value["audience"]
      issuer   = jwt_configuration.value["issuer"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "authorizer_result_ttl_in_seconds" {
  description = "returns a number"
  value       = aws_apigatewayv2_authorizer.this.authorizer_result_ttl_in_seconds
}

output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_authorizer.this.id
}

output "this" {
  value = aws_apigatewayv2_authorizer.this
}
```
[top](#index)
