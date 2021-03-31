# fortios_system_passwordpolicy

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
module "fortios_system_passwordpolicy" {
  source = "./modules/fortios/r/fortios_system_passwordpolicy"

  # apply_to - (optional) is a type of string
  apply_to = null
  # change_4_characters - (optional) is a type of string
  change_4_characters = null
  # expire_day - (optional) is a type of number
  expire_day = null
  # expire_status - (optional) is a type of string
  expire_status = null
  # min_lower_case_letter - (optional) is a type of number
  min_lower_case_letter = null
  # min_non_alphanumeric - (optional) is a type of number
  min_non_alphanumeric = null
  # min_number - (optional) is a type of number
  min_number = null
  # min_upper_case_letter - (optional) is a type of number
  min_upper_case_letter = null
  # minimum_length - (optional) is a type of number
  minimum_length = null
  # reuse_password - (optional) is a type of string
  reuse_password = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "apply_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "change_4_characters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expire_day" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "expire_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_lower_case_letter" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_non_alphanumeric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_upper_case_letter" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minimum_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reuse_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_passwordpolicy" "this" {
  apply_to              = var.apply_to
  change_4_characters   = var.change_4_characters
  expire_day            = var.expire_day
  expire_status         = var.expire_status
  min_lower_case_letter = var.min_lower_case_letter
  min_non_alphanumeric  = var.min_non_alphanumeric
  min_number            = var.min_number
  min_upper_case_letter = var.min_upper_case_letter
  minimum_length        = var.minimum_length
  reuse_password        = var.reuse_password
  status                = var.status
}
```

[top](#index)

### Outputs

```terraform
output "apply_to" {
  description = "returns a string"
  value       = fortios_system_passwordpolicy.this.apply_to
}

output "change_4_characters" {
  description = "returns a string"
  value       = fortios_system_passwordpolicy.this.change_4_characters
}

output "expire_day" {
  description = "returns a number"
  value       = fortios_system_passwordpolicy.this.expire_day
}

output "expire_status" {
  description = "returns a string"
  value       = fortios_system_passwordpolicy.this.expire_status
}

output "id" {
  description = "returns a string"
  value       = fortios_system_passwordpolicy.this.id
}

output "min_lower_case_letter" {
  description = "returns a number"
  value       = fortios_system_passwordpolicy.this.min_lower_case_letter
}

output "min_non_alphanumeric" {
  description = "returns a number"
  value       = fortios_system_passwordpolicy.this.min_non_alphanumeric
}

output "min_number" {
  description = "returns a number"
  value       = fortios_system_passwordpolicy.this.min_number
}

output "min_upper_case_letter" {
  description = "returns a number"
  value       = fortios_system_passwordpolicy.this.min_upper_case_letter
}

output "minimum_length" {
  description = "returns a number"
  value       = fortios_system_passwordpolicy.this.minimum_length
}

output "reuse_password" {
  description = "returns a string"
  value       = fortios_system_passwordpolicy.this.reuse_password
}

output "status" {
  description = "returns a string"
  value       = fortios_system_passwordpolicy.this.status
}

output "this" {
  value = fortios_system_passwordpolicy.this
}
```

[top](#index)