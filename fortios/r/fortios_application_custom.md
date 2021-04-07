# fortios_application_custom

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_application_custom" {
  source = "./modules/fortios/r/fortios_application_custom"

  # behavior - (optional) is a type of string
  behavior = null
  # category - (required) is a type of number
  category = null
  # comment - (optional) is a type of string
  comment = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # signature - (optional) is a type of string
  signature = null
  # tag - (optional) is a type of string
  tag = null
  # technology - (optional) is a type of string
  technology = null
  # vendor - (optional) is a type of string
  vendor = null
}
```

[top](#index)

### Variables

```terraform
variable "behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(required)"
  type        = number
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "technology" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_application_custom" "this" {
  # behavior - (optional) is a type of string
  behavior = var.behavior
  # category - (required) is a type of number
  category = var.category
  # comment - (optional) is a type of string
  comment = var.comment
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # name - (optional) is a type of string
  name = var.name
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # signature - (optional) is a type of string
  signature = var.signature
  # tag - (optional) is a type of string
  tag = var.tag
  # technology - (optional) is a type of string
  technology = var.technology
  # vendor - (optional) is a type of string
  vendor = var.vendor
}
```

[top](#index)

### Outputs

```terraform
output "behavior" {
  description = "returns a string"
  value       = fortios_application_custom.this.behavior
}

output "comment" {
  description = "returns a string"
  value       = fortios_application_custom.this.comment
}

output "fosid" {
  description = "returns a number"
  value       = fortios_application_custom.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_application_custom.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_application_custom.this.name
}

output "protocol" {
  description = "returns a string"
  value       = fortios_application_custom.this.protocol
}

output "signature" {
  description = "returns a string"
  value       = fortios_application_custom.this.signature
}

output "tag" {
  description = "returns a string"
  value       = fortios_application_custom.this.tag
}

output "technology" {
  description = "returns a string"
  value       = fortios_application_custom.this.technology
}

output "vendor" {
  description = "returns a string"
  value       = fortios_application_custom.this.vendor
}

output "this" {
  value = fortios_application_custom.this
}
```

[top](#index)