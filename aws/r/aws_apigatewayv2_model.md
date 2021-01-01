# aws_apigatewayv2_model
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
module "aws_apigatewayv2_model" {
  source = "./modules/aws/r/aws_apigatewayv2_model"

  # api_id - (required) is a type of string
  api_id = null
  # content_type - (required) is a type of string
  content_type = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # schema - (required) is a type of string
  schema = null
}
```
[top](#index)
### Variables
```hcl
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "content_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_apigatewayv2_model" "this" {
  api_id       = var.api_id
  content_type = var.content_type
  description  = var.description
  name         = var.name
  schema       = var.schema
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_model.this.id
}

output "this" {
  value = aws_apigatewayv2_model.this
}
```
[top](#index)
