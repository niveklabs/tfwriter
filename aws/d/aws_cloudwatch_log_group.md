# aws_cloudwatch_log_group
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
module "aws_cloudwatch_log_group" {
  source = "./modules/aws/d/aws_cloudwatch_log_group"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
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

### Datasource
```hcl
data "aws_cloudwatch_log_group" "this" {
  name = var.name
  tags = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_cloudwatch_log_group.this.arn
}

output "creation_time" {
  description = "returns a number"
  value       = data.aws_cloudwatch_log_group.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudwatch_log_group.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_cloudwatch_log_group.this.kms_key_id
}

output "retention_in_days" {
  description = "returns a number"
  value       = data.aws_cloudwatch_log_group.this.retention_in_days
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_cloudwatch_log_group.this.tags
}

output "this" {
  value = aws_cloudwatch_log_group.this
}
```
[top](#index)
