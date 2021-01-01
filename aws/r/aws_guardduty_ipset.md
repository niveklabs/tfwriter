# aws_guardduty_ipset
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
module "aws_guardduty_ipset" {
  source = "./modules/aws/r/aws_guardduty_ipset"

  # activate - (required) is a type of bool
  activate = null
  # detector_id - (required) is a type of string
  detector_id = null
  # format - (required) is a type of string
  format = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "activate" {
  description = "(required)"
  type        = bool
}

variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "format" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
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
```
[top](#index)

### Resource
```hcl
resource "aws_guardduty_ipset" "this" {
  activate    = var.activate
  detector_id = var.detector_id
  format      = var.format
  location    = var.location
  name        = var.name
  tags        = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_guardduty_ipset.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_guardduty_ipset.this.id
}

output "this" {
  value = aws_guardduty_ipset.this
}
```
[top](#index)
