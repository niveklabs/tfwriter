# aws_cognito_identity_provider
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
module "aws_cognito_identity_provider" {
  source = "./modules/aws/r/aws_cognito_identity_provider"

  # attribute_mapping - (optional) is a type of map of string
  attribute_mapping = {}
  # idp_identifiers - (optional) is a type of list of string
  idp_identifiers = []
  # provider_details - (required) is a type of map of string
  provider_details = {}
  # provider_name - (required) is a type of string
  provider_name = null
  # provider_type - (required) is a type of string
  provider_type = null
  # user_pool_id - (required) is a type of string
  user_pool_id = null
}
```
[top](#index)
### Variables
```hcl
variable "attribute_mapping" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "idp_identifiers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "provider_details" {
  description = "(required)"
  type        = map(string)
}

variable "provider_name" {
  description = "(required)"
  type        = string
}

variable "provider_type" {
  description = "(required)"
  type        = string
}

variable "user_pool_id" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_cognito_identity_provider" "this" {
  attribute_mapping = var.attribute_mapping
  idp_identifiers   = var.idp_identifiers
  provider_details  = var.provider_details
  provider_name     = var.provider_name
  provider_type     = var.provider_type
  user_pool_id      = var.user_pool_id
}
```
[top](#index)
### Outputs
```hcl
output "attribute_mapping" {
  description = "returns a map of string"
  value       = aws_cognito_identity_provider.this.attribute_mapping
}

output "id" {
  description = "returns a string"
  value       = aws_cognito_identity_provider.this.id
}

output "this" {
  value = aws_cognito_identity_provider.this
}
```
[top](#index)
