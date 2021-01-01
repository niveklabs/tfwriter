# aws_api_gateway_vpc_link
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
module "aws_api_gateway_vpc_link" {
  source = "./modules/aws/r/aws_api_gateway_vpc_link"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_arns - (required) is a type of list of string
  target_arns = []
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_arns" {
  description = "(required)"
  type        = list(string)
}
```
[top](#index)

### Resource
```hcl
resource "aws_api_gateway_vpc_link" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags
  target_arns = var.target_arns
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_vpc_link.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_vpc_link.this.id
}

output "this" {
  value = aws_api_gateway_vpc_link.this
}
```
[top](#index)
