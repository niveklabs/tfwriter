# aws_apigatewayv2_api_mapping
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
module "aws_apigatewayv2_api_mapping" {
  source = "./modules/aws/r/aws_apigatewayv2_api_mapping"

  # api_id - (required) is a type of string
  api_id = null
  # api_mapping_key - (optional) is a type of string
  api_mapping_key = null
  # domain_name - (required) is a type of string
  domain_name = null
  # stage - (required) is a type of string
  stage = null
}
```
[top](#index)
### Variables
```hcl
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "api_mapping_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "stage" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_apigatewayv2_api_mapping" "this" {
  api_id          = var.api_id
  api_mapping_key = var.api_mapping_key
  domain_name     = var.domain_name
  stage           = var.stage
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_api_mapping.this.id
}

output "this" {
  value = aws_apigatewayv2_api_mapping.this
}
```
[top](#index)
