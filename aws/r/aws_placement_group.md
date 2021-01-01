# aws_placement_group
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
module "aws_placement_group" {
  source = "./modules/aws/r/aws_placement_group"

  # name - (required) is a type of string
  name = null
  # strategy - (required) is a type of string
  strategy = null
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

variable "strategy" {
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
resource "aws_placement_group" "this" {
  name     = var.name
  strategy = var.strategy
  tags     = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_placement_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_placement_group.this.id
}

output "placement_group_id" {
  description = "returns a string"
  value       = aws_placement_group.this.placement_group_id
}

output "this" {
  value = aws_placement_group.this
}
```
[top](#index)
