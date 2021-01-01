# aws_wafv2_web_acl
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
module "aws_wafv2_web_acl" {
  source = "./modules/aws/d/aws_wafv2_web_acl"

  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_wafv2_web_acl" "this" {
  name  = var.name
  scope = var.scope
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_wafv2_web_acl.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_wafv2_web_acl.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_wafv2_web_acl.this.id
}

output "this" {
  value = aws_wafv2_web_acl.this
}
```
[top](#index)
