# aws_imagebuilder_component
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
module "aws_imagebuilder_component" {
  source = "./modules/aws/r/aws_imagebuilder_component"

  # change_description - (optional) is a type of string
  change_description = null
  # data - (optional) is a type of string
  data = null
  # description - (optional) is a type of string
  description = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (required) is a type of string
  name = null
  # platform - (required) is a type of string
  platform = null
  # supported_os_versions - (optional) is a type of set of string
  supported_os_versions = []
  # tags - (optional) is a type of map of string
  tags = {}
  # uri - (optional) is a type of string
  uri = null
  # version - (required) is a type of string
  version = null
}
```
[top](#index)
### Variables
```hcl
variable "change_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform" {
  description = "(required)"
  type        = string
}

variable "supported_os_versions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_imagebuilder_component" "this" {
  change_description    = var.change_description
  data                  = var.data
  description           = var.description
  kms_key_id            = var.kms_key_id
  name                  = var.name
  platform              = var.platform
  supported_os_versions = var.supported_os_versions
  tags                  = var.tags
  uri                   = var.uri
  version               = var.version
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_imagebuilder_component.this.arn
}

output "data" {
  description = "returns a string"
  value       = aws_imagebuilder_component.this.data
}

output "date_created" {
  description = "returns a string"
  value       = aws_imagebuilder_component.this.date_created
}

output "encrypted" {
  description = "returns a bool"
  value       = aws_imagebuilder_component.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = aws_imagebuilder_component.this.id
}

output "owner" {
  description = "returns a string"
  value       = aws_imagebuilder_component.this.owner
}

output "type" {
  description = "returns a string"
  value       = aws_imagebuilder_component.this.type
}

output "this" {
  value = aws_imagebuilder_component.this
}
```
[top](#index)
