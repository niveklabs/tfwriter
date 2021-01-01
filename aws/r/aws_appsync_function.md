# aws_appsync_function
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
module "aws_appsync_function" {
  source = "./modules/aws/r/aws_appsync_function"

  # api_id - (required) is a type of string
  api_id = null
  # data_source - (required) is a type of string
  data_source = null
  # description - (optional) is a type of string
  description = null
  # function_version - (optional) is a type of string
  function_version = null
  # name - (required) is a type of string
  name = null
  # request_mapping_template - (required) is a type of string
  request_mapping_template = null
  # response_mapping_template - (required) is a type of string
  response_mapping_template = null
}
```
[top](#index)
### Variables
```hcl
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "data_source" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "function_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "request_mapping_template" {
  description = "(required)"
  type        = string
}

variable "response_mapping_template" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_appsync_function" "this" {
  api_id                    = var.api_id
  data_source               = var.data_source
  description               = var.description
  function_version          = var.function_version
  name                      = var.name
  request_mapping_template  = var.request_mapping_template
  response_mapping_template = var.response_mapping_template
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_appsync_function.this.arn
}

output "function_id" {
  description = "returns a string"
  value       = aws_appsync_function.this.function_id
}

output "id" {
  description = "returns a string"
  value       = aws_appsync_function.this.id
}

output "this" {
  value = aws_appsync_function.this
}
```
[top](#index)
