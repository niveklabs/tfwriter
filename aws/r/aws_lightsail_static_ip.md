# aws_lightsail_static_ip
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
module "aws_lightsail_static_ip" {
  source = "./modules/aws/r/aws_lightsail_static_ip"

  # name - (required) is a type of string
  name = null
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_lightsail_static_ip" "this" {
  name = var.name
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_lightsail_static_ip.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_lightsail_static_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = aws_lightsail_static_ip.this.ip_address
}

output "support_code" {
  description = "returns a string"
  value       = aws_lightsail_static_ip.this.support_code
}

output "this" {
  value = aws_lightsail_static_ip.this
}
```
[top](#index)
