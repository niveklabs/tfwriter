# fortios_logfortiguard_overridesetting

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_logfortiguard_overridesetting" {
  source = "./modules/fortios/r/fortios_logfortiguard_overridesetting"

  # override - (optional) is a type of string
  override = null
  # status - (optional) is a type of string
  status = null
  # upload_day - (optional) is a type of string
  upload_day = null
  # upload_interval - (optional) is a type of string
  upload_interval = null
  # upload_option - (optional) is a type of string
  upload_option = null
  # upload_time - (optional) is a type of string
  upload_time = null
}
```

[top](#index)

### Variables

```terraform
variable "override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortiguard_overridesetting" "this" {
  override        = var.override
  status          = var.status
  upload_day      = var.upload_day
  upload_interval = var.upload_interval
  upload_option   = var.upload_option
  upload_time     = var.upload_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.id
}

output "override" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.override
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.status
}

output "upload_day" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.upload_day
}

output "upload_interval" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.upload_interval
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.upload_option
}

output "upload_time" {
  description = "returns a string"
  value       = fortios_logfortiguard_overridesetting.this.upload_time
}

output "this" {
  value = fortios_logfortiguard_overridesetting.this
}
```

[top](#index)