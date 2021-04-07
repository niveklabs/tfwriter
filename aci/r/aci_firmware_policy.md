# aci_firmware_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_firmware_policy" {
  source = "./modules/aci/r/aci_firmware_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # effective_on_reboot - (optional) is a type of string
  effective_on_reboot = null
  # ignore_compat - (optional) is a type of string
  ignore_compat = null
  # internal_label - (optional) is a type of string
  internal_label = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # version - (optional) is a type of string
  version = null
  # version_check_override - (optional) is a type of string
  version_check_override = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "effective_on_reboot" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_compat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internal_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_check_override" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_firmware_policy" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # effective_on_reboot - (optional) is a type of string
  effective_on_reboot = var.effective_on_reboot
  # ignore_compat - (optional) is a type of string
  ignore_compat = var.ignore_compat
  # internal_label - (optional) is a type of string
  internal_label = var.internal_label
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # version - (optional) is a type of string
  version = var.version
  # version_check_override - (optional) is a type of string
  version_check_override = var.version_check_override
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_firmware_policy.this.description
}

output "effective_on_reboot" {
  description = "returns a string"
  value       = aci_firmware_policy.this.effective_on_reboot
}

output "id" {
  description = "returns a string"
  value       = aci_firmware_policy.this.id
}

output "ignore_compat" {
  description = "returns a string"
  value       = aci_firmware_policy.this.ignore_compat
}

output "internal_label" {
  description = "returns a string"
  value       = aci_firmware_policy.this.internal_label
}

output "name_alias" {
  description = "returns a string"
  value       = aci_firmware_policy.this.name_alias
}

output "version" {
  description = "returns a string"
  value       = aci_firmware_policy.this.version
}

output "version_check_override" {
  description = "returns a string"
  value       = aci_firmware_policy.this.version_check_override
}

output "this" {
  value = aci_firmware_policy.this
}
```

[top](#index)