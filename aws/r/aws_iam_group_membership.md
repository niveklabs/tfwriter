# aws_iam_group_membership
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
module "aws_iam_group_membership" {
  source = "./modules/aws/r/aws_iam_group_membership"

  # group - (required) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
  # users - (required) is a type of set of string
  users = []
}
```
[top](#index)
### Variables
```hcl
variable "group" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "users" {
  description = "(required)"
  type        = set(string)
}
```
[top](#index)

### Resource
```hcl
resource "aws_iam_group_membership" "this" {
  group = var.group
  name  = var.name
  users = var.users
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_iam_group_membership.this.id
}

output "this" {
  value = aws_iam_group_membership.this
}
```
[top](#index)
