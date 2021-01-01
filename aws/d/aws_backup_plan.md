# aws_backup_plan
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
module "aws_backup_plan" {
  source = "./modules/aws/d/aws_backup_plan"

  # plan_id - (required) is a type of string
  plan_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "plan_id" {
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

### Datasource
```hcl
data "aws_backup_plan" "this" {
  plan_id = var.plan_id
  tags    = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.name
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_backup_plan.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.version
}

output "this" {
  value = aws_backup_plan.this
}
```
[top](#index)
