# aws_customer_gateway
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
module "aws_customer_gateway" {
  source = "./modules/aws/r/aws_customer_gateway"

  # bgp_asn - (required) is a type of string
  bgp_asn = null
  # ip_address - (required) is a type of string
  ip_address = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
}
```
[top](#index)
### Variables
```hcl
variable "bgp_asn" {
  description = "(required)"
  type        = string
}

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_customer_gateway" "this" {
  bgp_asn    = var.bgp_asn
  ip_address = var.ip_address
  tags       = var.tags
  type       = var.type
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_customer_gateway.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_customer_gateway.this.id
}

output "this" {
  value = aws_customer_gateway.this
}
```
[top](#index)
