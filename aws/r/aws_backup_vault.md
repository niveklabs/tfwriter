# aws_backup_vault
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
module "aws_backup_vault" {
  source = "./modules/aws/r/aws_backup_vault"

  # kms_key_arn - (optional) is a type of string
  kms_key_arn = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "aws_backup_vault" "this" {
  kms_key_arn = var.kms_key_arn
  name        = var.name
  tags        = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_backup_vault.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_backup_vault.this.id
}

output "kms_key_arn" {
  description = "returns a string"
  value       = aws_backup_vault.this.kms_key_arn
}

output "recovery_points" {
  description = "returns a number"
  value       = aws_backup_vault.this.recovery_points
}

output "this" {
  value = aws_backup_vault.this
}
```
[top](#index)
