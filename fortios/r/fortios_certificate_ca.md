# fortios_certificate_ca

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
module "fortios_certificate_ca" {
  source = null

  # auto_update_days - (optional) is a type of number
  auto_update_days = null
  # auto_update_days_warning - (optional) is a type of number
  auto_update_days_warning = null
  # ca - (required) is a type of string
  ca = null
  # last_updated - (optional) is a type of number
  last_updated = null
  # name - (required) is a type of string
  name = null
  # range - (optional) is a type of string
  range = null
  # scep_url - (optional) is a type of string
  scep_url = null
  # source - (optional) is a type of string
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_inspection_trusted - (optional) is a type of string
  ssl_inspection_trusted = null
  # trusted - (optional) is a type of string
  trusted = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_update_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_update_days_warning" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ca" {
  description = "(required)"
  type        = string
}

variable "last_updated" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scep_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_inspection_trusted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusted" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_certificate_ca" "this" {
  # auto_update_days - (optional) is a type of number
  auto_update_days = var.auto_update_days
  # auto_update_days_warning - (optional) is a type of number
  auto_update_days_warning = var.auto_update_days_warning
  # ca - (required) is a type of string
  ca = var.ca
  # last_updated - (optional) is a type of number
  last_updated = var.last_updated
  # name - (required) is a type of string
  name = var.name
  # range - (optional) is a type of string
  range = var.range
  # scep_url - (optional) is a type of string
  scep_url = var.scep_url
  # source - (optional) is a type of string
  source = var.source
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # ssl_inspection_trusted - (optional) is a type of string
  ssl_inspection_trusted = var.ssl_inspection_trusted
  # trusted - (optional) is a type of string
  trusted = var.trusted
}
```

[top](#index)

### Outputs

```terraform
output "auto_update_days" {
  description = "returns a number"
  value       = fortios_certificate_ca.this.auto_update_days
}

output "auto_update_days_warning" {
  description = "returns a number"
  value       = fortios_certificate_ca.this.auto_update_days_warning
}

output "id" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.id
}

output "last_updated" {
  description = "returns a number"
  value       = fortios_certificate_ca.this.last_updated
}

output "range" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.range
}

output "scep_url" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.scep_url
}

output "source" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.source
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.source_ip
}

output "ssl_inspection_trusted" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.ssl_inspection_trusted
}

output "trusted" {
  description = "returns a string"
  value       = fortios_certificate_ca.this.trusted
}

output "this" {
  value = fortios_certificate_ca.this
}
```

[top](#index)