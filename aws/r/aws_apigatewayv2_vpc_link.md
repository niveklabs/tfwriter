# aws_apigatewayv2_vpc_link
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
module "aws_apigatewayv2_vpc_link" {
  source = "./modules/aws/r/aws_apigatewayv2_vpc_link"

  # name - (required) is a type of string
  name = null
  # security_group_ids - (required) is a type of set of string
  security_group_ids = []
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
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

variable "security_group_ids" {
  description = "(required)"
  type        = set(string)
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
resource "aws_apigatewayv2_vpc_link" "this" {
  name               = var.name
  security_group_ids = var.security_group_ids
  subnet_ids         = var.subnet_ids
  tags               = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_apigatewayv2_vpc_link.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_vpc_link.this.id
}

output "this" {
  value = aws_apigatewayv2_vpc_link.this
}
```
[top](#index)
