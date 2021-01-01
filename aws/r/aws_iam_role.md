# aws_iam_role
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
module "aws_iam_role" {
  source = "./modules/aws/r/aws_iam_role"

  # assume_role_policy - (required) is a type of string
  assume_role_policy = null
  # description - (optional) is a type of string
  description = null
  # force_detach_policies - (optional) is a type of bool
  force_detach_policies = null
  # max_session_duration - (optional) is a type of number
  max_session_duration = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path - (optional) is a type of string
  path = null
  # permissions_boundary - (optional) is a type of string
  permissions_boundary = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "assume_role_policy" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_detach_policies" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_session_duration" {
  description = "(optional)"
  type        = number
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

variable "permissions_boundary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```
[top](#index)

### Resource
```hcl
resource "aws_iam_role" "this" {
  assume_role_policy    = var.assume_role_policy
  description           = var.description
  force_detach_policies = var.force_detach_policies
  max_session_duration  = var.max_session_duration
  name                  = var.name
  name_prefix           = var.name_prefix
  path                  = var.path
  permissions_boundary  = var.permissions_boundary
  tags                  = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_iam_role.this.arn
}

output "create_date" {
  description = "returns a string"
  value       = aws_iam_role.this.create_date
}

output "id" {
  description = "returns a string"
  value       = aws_iam_role.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_role.this.name
}

output "unique_id" {
  description = "returns a string"
  value       = aws_iam_role.this.unique_id
}

output "this" {
  value = aws_iam_role.this
}
```
[top](#index)
