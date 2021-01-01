# aws_lambda_code_signing_config
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_lambda_code_signing_config" {
  source = "./modules/aws/d/aws_lambda_code_signing_config"

  # arn - (required) is a type of string
  arn = null
}
```
[top](#index)
### Variables
```hcl
variable "arn" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_lambda_code_signing_config" "this" {
  arn = var.arn
}
```
[top](#index)
### Outputs
```hcl
output "allowed_publishers" {
  description = "returns a list of object"
  value       = data.aws_lambda_code_signing_config.this.allowed_publishers
}

output "config_id" {
  description = "returns a string"
  value       = data.aws_lambda_code_signing_config.this.config_id
}

output "description" {
  description = "returns a string"
  value       = data.aws_lambda_code_signing_config.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_lambda_code_signing_config.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = data.aws_lambda_code_signing_config.this.last_modified
}

output "policies" {
  description = "returns a list of object"
  value       = data.aws_lambda_code_signing_config.this.policies
}

output "this" {
  value = aws_lambda_code_signing_config.this
}
```
[top](#index)
