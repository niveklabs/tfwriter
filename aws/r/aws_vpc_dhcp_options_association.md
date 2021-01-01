# aws_vpc_dhcp_options_association
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
module "aws_vpc_dhcp_options_association" {
  source = "./modules/aws/r/aws_vpc_dhcp_options_association"

  # dhcp_options_id - (required) is a type of string
  dhcp_options_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```
[top](#index)
### Variables
```hcl
variable "dhcp_options_id" {
  description = "(required)"
  type        = string
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_vpc_dhcp_options_association" "this" {
  dhcp_options_id = var.dhcp_options_id
  vpc_id          = var.vpc_id
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_vpc_dhcp_options_association.this.id
}

output "this" {
  value = aws_vpc_dhcp_options_association.this
}
```
[top](#index)
