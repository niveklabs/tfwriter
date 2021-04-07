# fortios_webfilter_override

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
module "fortios_webfilter_override" {
  source = "./modules/fortios/r/fortios_webfilter_override"

  # expires - (required) is a type of string
  expires = null
  # fosid - (optional) is a type of number
  fosid = null
  # initiator - (optional) is a type of string
  initiator = null
  # ip - (optional) is a type of string
  ip = null
  # ip6 - (optional) is a type of string
  ip6 = null
  # new_profile - (required) is a type of string
  new_profile = null
  # old_profile - (required) is a type of string
  old_profile = null
  # scope - (optional) is a type of string
  scope = null
  # status - (optional) is a type of string
  status = null
  # user - (required) is a type of string
  user = null
  # user_group - (optional) is a type of string
  user_group = null
}
```

[top](#index)

### Variables

```terraform
variable "expires" {
  description = "(required)"
  type        = string
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "initiator" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "new_profile" {
  description = "(required)"
  type        = string
}

variable "old_profile" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(required)"
  type        = string
}

variable "user_group" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_override" "this" {
  # expires - (required) is a type of string
  expires = var.expires
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # initiator - (optional) is a type of string
  initiator = var.initiator
  # ip - (optional) is a type of string
  ip = var.ip
  # ip6 - (optional) is a type of string
  ip6 = var.ip6
  # new_profile - (required) is a type of string
  new_profile = var.new_profile
  # old_profile - (required) is a type of string
  old_profile = var.old_profile
  # scope - (optional) is a type of string
  scope = var.scope
  # status - (optional) is a type of string
  status = var.status
  # user - (required) is a type of string
  user = var.user
  # user_group - (optional) is a type of string
  user_group = var.user_group
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_webfilter_override.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.id
}

output "initiator" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.initiator
}

output "ip" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.ip
}

output "ip6" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.ip6
}

output "scope" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.scope
}

output "status" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.status
}

output "user_group" {
  description = "returns a string"
  value       = fortios_webfilter_override.this.user_group
}

output "this" {
  value = fortios_webfilter_override.this
}
```

[top](#index)