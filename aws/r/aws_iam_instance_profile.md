# aws_iam_instance_profile
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
module "aws_iam_instance_profile" {
  source = "./modules/aws/r/aws_iam_instance_profile"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path - (optional) is a type of string
  path = null
  # role - (optional) is a type of string
  role = null
}
```
[top](#index)
### Variables
```hcl
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

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}
```
[top](#index)

### Resource
```hcl
resource "aws_iam_instance_profile" "this" {
  name        = var.name
  name_prefix = var.name_prefix
  path        = var.path
  role        = var.role
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.arn
}

output "create_date" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.create_date
}

output "id" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.name
}

output "unique_id" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.unique_id
}

output "this" {
  value = aws_iam_instance_profile.this
}
```
[top](#index)
