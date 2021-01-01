# aws_lex_bot_alias
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
module "aws_lex_bot_alias" {
  source = "./modules/aws/d/aws_lex_bot_alias"

  # bot_name - (required) is a type of string
  bot_name = null
  # name - (required) is a type of string
  name = null
}
```
[top](#index)
### Variables
```hcl
variable "bot_name" {
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
data "aws_lex_bot_alias" "this" {
  bot_name = var.bot_name
  name     = var.name
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.arn
}

output "bot_version" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.bot_version
}

output "checksum" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.created_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = data.aws_lex_bot_alias.this.last_updated_date
}

output "this" {
  value = aws_lex_bot_alias.this
}
```
[top](#index)
