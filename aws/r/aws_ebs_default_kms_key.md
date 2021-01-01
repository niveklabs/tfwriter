# aws_ebs_default_kms_key
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
module "aws_ebs_default_kms_key" {
  source = "./modules/aws/r/aws_ebs_default_kms_key"

  # key_arn - (required) is a type of string
  key_arn = null
}
```
[top](#index)
### Variables
```hcl
variable "key_arn" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_ebs_default_kms_key" "this" {
  key_arn = var.key_arn
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_ebs_default_kms_key.this.id
}

output "this" {
  value = aws_ebs_default_kms_key.this
}
```
[top](#index)
