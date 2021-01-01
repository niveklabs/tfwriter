# aws_servicequotas_service_quota
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
module "aws_servicequotas_service_quota" {
  source = "./modules/aws/r/aws_servicequotas_service_quota"

  # quota_code - (required) is a type of string
  quota_code = null
  # service_code - (required) is a type of string
  service_code = null
  # value - (required) is a type of number
  value = null
}
```
[top](#index)
### Variables
```hcl
variable "quota_code" {
  description = "(required)"
  type        = string
}

variable "service_code" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = number
}
```
[top](#index)

### Resource
```hcl
resource "aws_servicequotas_service_quota" "this" {
  quota_code   = var.quota_code
  service_code = var.service_code
  value        = var.value
}
```
[top](#index)
### Outputs
```hcl
output "adjustable" {
  description = "returns a bool"
  value       = aws_servicequotas_service_quota.this.adjustable
}

output "arn" {
  description = "returns a string"
  value       = aws_servicequotas_service_quota.this.arn
}

output "default_value" {
  description = "returns a number"
  value       = aws_servicequotas_service_quota.this.default_value
}

output "id" {
  description = "returns a string"
  value       = aws_servicequotas_service_quota.this.id
}

output "quota_name" {
  description = "returns a string"
  value       = aws_servicequotas_service_quota.this.quota_name
}

output "request_id" {
  description = "returns a string"
  value       = aws_servicequotas_service_quota.this.request_id
}

output "request_status" {
  description = "returns a string"
  value       = aws_servicequotas_service_quota.this.request_status
}

output "service_name" {
  description = "returns a string"
  value       = aws_servicequotas_service_quota.this.service_name
}

output "this" {
  value = aws_servicequotas_service_quota.this
}
```
[top](#index)
