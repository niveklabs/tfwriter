# aws_lambda_alias
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
module "aws_lambda_alias" {
  source = "./modules/aws/d/aws_lambda_alias"

  # function_name - (required) is a type of string
  function_name = null
  # name - (required) is a type of string
  name = null
}
```
[top](#index)
### Variables
```hcl
variable "function_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_lambda_alias" "this" {
  function_name = var.function_name
  name          = var.name
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_lambda_alias.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_lambda_alias.this.description
}

output "function_version" {
  description = "returns a string"
  value       = data.aws_lambda_alias.this.function_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_lambda_alias.this.id
}

output "invoke_arn" {
  description = "returns a string"
  value       = data.aws_lambda_alias.this.invoke_arn
}

output "this" {
  value = aws_lambda_alias.this
}
```
[top](#index)
