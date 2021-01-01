# aws_iam_openid_connect_provider
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
module "aws_iam_openid_connect_provider" {
  source = "./modules/aws/r/aws_iam_openid_connect_provider"

  # client_id_list - (required) is a type of list of string
  client_id_list = []
  # thumbprint_list - (required) is a type of list of string
  thumbprint_list = []
  # url - (required) is a type of string
  url = null
}
```
[top](#index)
### Variables
```hcl
variable "client_id_list" {
  description = "(required)"
  type        = list(string)
}

variable "thumbprint_list" {
  description = "(required)"
  type        = list(string)
}

variable "url" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_iam_openid_connect_provider" "this" {
  client_id_list  = var.client_id_list
  thumbprint_list = var.thumbprint_list
  url             = var.url
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_iam_openid_connect_provider.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_openid_connect_provider.this.id
}

output "this" {
  value = aws_iam_openid_connect_provider.this
}
```
[top](#index)
