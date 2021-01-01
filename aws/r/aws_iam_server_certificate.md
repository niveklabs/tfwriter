# aws_iam_server_certificate
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
module "aws_iam_server_certificate" {
  source = "./modules/aws/r/aws_iam_server_certificate"

  # arn - (optional) is a type of string
  arn = null
  # certificate_body - (required) is a type of string
  certificate_body = null
  # certificate_chain - (optional) is a type of string
  certificate_chain = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path - (optional) is a type of string
  path = null
  # private_key - (required) is a type of string
  private_key = null
}
```
[top](#index)
### Variables
```hcl
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_body" {
  description = "(required)"
  type        = string
}

variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_iam_server_certificate" "this" {
  arn               = var.arn
  certificate_body  = var.certificate_body
  certificate_chain = var.certificate_chain
  name              = var.name
  name_prefix       = var.name_prefix
  path              = var.path
  private_key       = var.private_key
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_server_certificate.this.name
}

output "this" {
  value = aws_iam_server_certificate.this
}
```
[top](#index)
