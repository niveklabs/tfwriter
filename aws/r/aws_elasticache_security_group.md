# aws_elasticache_security_group
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
module "aws_elasticache_security_group" {
  source = "./modules/aws/r/aws_elasticache_security_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # security_group_names - (required) is a type of set of string
  security_group_names = []
}
```
[top](#index)
### Variables
```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "security_group_names" {
  description = "(required)"
  type        = set(string)
}
```
[top](#index)

### Resource
```hcl
resource "aws_elasticache_security_group" "this" {
  description          = var.description
  name                 = var.name
  security_group_names = var.security_group_names
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_elasticache_security_group.this.id
}

output "this" {
  value = aws_elasticache_security_group.this
}
```
[top](#index)
