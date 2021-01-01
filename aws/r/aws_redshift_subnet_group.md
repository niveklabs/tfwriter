# aws_redshift_subnet_group
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
module "aws_redshift_subnet_group" {
  source = "./modules/aws/r/aws_redshift_subnet_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
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
resource "aws_redshift_subnet_group" "this" {
  description = var.description
  name        = var.name
  subnet_ids  = var.subnet_ids
  tags        = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_redshift_subnet_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_redshift_subnet_group.this.id
}

output "this" {
  value = aws_redshift_subnet_group.this
}
```
[top](#index)
