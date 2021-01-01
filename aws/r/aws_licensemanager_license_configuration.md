# aws_licensemanager_license_configuration
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
module "aws_licensemanager_license_configuration" {
  source = "./modules/aws/r/aws_licensemanager_license_configuration"

  # description - (optional) is a type of string
  description = null
  # license_count - (optional) is a type of number
  license_count = null
  # license_count_hard_limit - (optional) is a type of bool
  license_count_hard_limit = null
  # license_counting_type - (required) is a type of string
  license_counting_type = null
  # license_rules - (optional) is a type of list of string
  license_rules = []
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "license_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "license_count_hard_limit" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_counting_type" {
  description = "(required)"
  type        = string
}

variable "license_rules" {
  description = "(optional)"
  type        = list(string)
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
```
[top](#index)

### Resource
```hcl
resource "aws_licensemanager_license_configuration" "this" {
  description              = var.description
  license_count            = var.license_count
  license_count_hard_limit = var.license_count_hard_limit
  license_counting_type    = var.license_counting_type
  license_rules            = var.license_rules
  name                     = var.name
  tags                     = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_licensemanager_license_configuration.this.id
}

output "this" {
  value = aws_licensemanager_license_configuration.this
}
```
[top](#index)
