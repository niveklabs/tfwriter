# aws_iot_policy
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
module "aws_iot_policy" {
  source = "./modules/aws/r/aws_iot_policy"

  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_iot_policy" "this" {
  name   = var.name
  policy = var.policy
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_iot_policy.this.arn
}

output "default_version_id" {
  description = "returns a string"
  value       = aws_iot_policy.this.default_version_id
}

output "id" {
  description = "returns a string"
  value       = aws_iot_policy.this.id
}

output "this" {
  value = aws_iot_policy.this
}
```
[top](#index)
