# aws_macie_member_account_association
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
module "aws_macie_member_account_association" {
  source = "./modules/aws/r/aws_macie_member_account_association"

  # member_account_id - (required) is a type of string
  member_account_id = null
}
```
[top](#index)
### Variables
```hcl
variable "member_account_id" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_macie_member_account_association" "this" {
  member_account_id = var.member_account_id
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_macie_member_account_association.this.id
}

output "this" {
  value = aws_macie_member_account_association.this
}
```
[top](#index)
