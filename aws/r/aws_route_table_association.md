# aws_route_table_association
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
module "aws_route_table_association" {
  source = "./modules/aws/r/aws_route_table_association"

  # gateway_id - (optional) is a type of string
  gateway_id = null
  # route_table_id - (required) is a type of string
  route_table_id = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
}
```
[top](#index)
### Variables
```hcl
variable "gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```
[top](#index)

### Resource
```hcl
resource "aws_route_table_association" "this" {
  gateway_id     = var.gateway_id
  route_table_id = var.route_table_id
  subnet_id      = var.subnet_id
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_route_table_association.this.id
}

output "this" {
  value = aws_route_table_association.this
}
```
[top](#index)
