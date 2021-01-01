# aws_quicksight_user
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
module "aws_quicksight_user" {
  source = "./modules/aws/r/aws_quicksight_user"

  # aws_account_id - (optional) is a type of string
  aws_account_id = null
  # email - (required) is a type of string
  email = null
  # iam_arn - (optional) is a type of string
  iam_arn = null
  # identity_type - (required) is a type of string
  identity_type = null
  # namespace - (optional) is a type of string
  namespace = null
  # session_name - (optional) is a type of string
  session_name = null
  # user_name - (optional) is a type of string
  user_name = null
  # user_role - (required) is a type of string
  user_role = null
}
```
[top](#index)
### Variables
```hcl
variable "aws_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "iam_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_type" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_role" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_quicksight_user" "this" {
  aws_account_id = var.aws_account_id
  email          = var.email
  iam_arn        = var.iam_arn
  identity_type  = var.identity_type
  namespace      = var.namespace
  session_name   = var.session_name
  user_name      = var.user_name
  user_role      = var.user_role
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_quicksight_user.this.arn
}

output "aws_account_id" {
  description = "returns a string"
  value       = aws_quicksight_user.this.aws_account_id
}

output "id" {
  description = "returns a string"
  value       = aws_quicksight_user.this.id
}

output "this" {
  value = aws_quicksight_user.this
}
```
[top](#index)
