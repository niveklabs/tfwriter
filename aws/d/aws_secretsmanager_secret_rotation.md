# aws_secretsmanager_secret_rotation
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
module "aws_secretsmanager_secret_rotation" {
  source = "./modules/aws/d/aws_secretsmanager_secret_rotation"

  # secret_id - (required) is a type of string
  secret_id = null
}
```
[top](#index)
### Variables
```hcl
variable "secret_id" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_secretsmanager_secret_rotation" "this" {
  secret_id = var.secret_id
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_rotation.this.id
}

output "rotation_enabled" {
  description = "returns a bool"
  value       = data.aws_secretsmanager_secret_rotation.this.rotation_enabled
}

output "rotation_lambda_arn" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_rotation.this.rotation_lambda_arn
}

output "rotation_rules" {
  description = "returns a list of object"
  value       = data.aws_secretsmanager_secret_rotation.this.rotation_rules
}

output "this" {
  value = aws_secretsmanager_secret_rotation.this
}
```
[top](#index)
