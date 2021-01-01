# aws_vpn_gateway_route_propagation
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
module "aws_vpn_gateway_route_propagation" {
  source = "./modules/aws/r/aws_vpn_gateway_route_propagation"

  # route_table_id - (required) is a type of string
  route_table_id = null
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null
}
```
[top](#index)
### Variables
```hcl
variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "vpn_gateway_id" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_vpn_gateway_route_propagation" "this" {
  route_table_id = var.route_table_id
  vpn_gateway_id = var.vpn_gateway_id
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_vpn_gateway_route_propagation.this.id
}

output "this" {
  value = aws_vpn_gateway_route_propagation.this
}
```
[top](#index)
