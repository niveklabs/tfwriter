# aws_ecr_lifecycle_policy
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
module "aws_ecr_lifecycle_policy" {
  source = "./modules/aws/r/aws_ecr_lifecycle_policy"

  # policy - (required) is a type of string
  policy = null
  # repository - (required) is a type of string
  repository = null
}
```
[top](#index)
### Variables
```hcl
variable "policy" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_ecr_lifecycle_policy" "this" {
  policy     = var.policy
  repository = var.repository
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_ecr_lifecycle_policy.this.id
}

output "registry_id" {
  description = "returns a string"
  value       = aws_ecr_lifecycle_policy.this.registry_id
}

output "this" {
  value = aws_ecr_lifecycle_policy.this
}
```
[top](#index)
