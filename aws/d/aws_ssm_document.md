# aws_ssm_document
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
module "aws_ssm_document" {
  source = "./modules/aws/d/aws_ssm_document"

  # document_format - (optional) is a type of string
  document_format = null
  # document_version - (optional) is a type of string
  document_version = null
  # name - (required) is a type of string
  name = null
}
```
[top](#index)
### Variables
```hcl
variable "document_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "document_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_ssm_document" "this" {
  document_format  = var.document_format
  document_version = var.document_version
  name             = var.name
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_ssm_document.this.arn
}

output "content" {
  description = "returns a string"
  value       = data.aws_ssm_document.this.content
}

output "document_type" {
  description = "returns a string"
  value       = data.aws_ssm_document.this.document_type
}

output "id" {
  description = "returns a string"
  value       = data.aws_ssm_document.this.id
}

output "this" {
  value = aws_ssm_document.this
}
```
[top](#index)
