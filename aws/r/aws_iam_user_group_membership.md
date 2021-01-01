# aws_iam_user_group_membership
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
module "aws_iam_user_group_membership" {
  source = "./modules/aws/r/aws_iam_user_group_membership"

  # groups - (required) is a type of set of string
  groups = []
  # user - (required) is a type of string
  user = null
}
```
[top](#index)
### Variables
```hcl
variable "groups" {
  description = "(required)"
  type        = set(string)
}

variable "user" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_iam_user_group_membership" "this" {
  groups = var.groups
  user   = var.user
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_iam_user_group_membership.this.id
}

output "this" {
  value = aws_iam_user_group_membership.this
}
```
[top](#index)
