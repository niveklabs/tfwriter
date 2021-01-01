# aws_lb_listener_certificate
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
module "aws_lb_listener_certificate" {
  source = "./modules/aws/r/aws_lb_listener_certificate"

  # certificate_arn - (required) is a type of string
  certificate_arn = null
  # listener_arn - (required) is a type of string
  listener_arn = null
}
```
[top](#index)
### Variables
```hcl
variable "certificate_arn" {
  description = "(required)"
  type        = string
}

variable "listener_arn" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_lb_listener_certificate" "this" {
  certificate_arn = var.certificate_arn
  listener_arn    = var.listener_arn
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_lb_listener_certificate.this.id
}

output "this" {
  value = aws_lb_listener_certificate.this
}
```
[top](#index)
