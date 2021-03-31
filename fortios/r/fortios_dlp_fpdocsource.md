# fortios_dlp_fpdocsource

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
module "fortios_dlp_fpdocsource" {
  source = "./modules/fortios/r/fortios_dlp_fpdocsource"

  # date - (optional) is a type of number
  date = null
  # file_path - (optional) is a type of string
  file_path = null
  # file_pattern - (optional) is a type of string
  file_pattern = null
  # keep_modified - (optional) is a type of string
  keep_modified = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # period - (optional) is a type of string
  period = null
  # remove_deleted - (optional) is a type of string
  remove_deleted = null
  # scan_on_creation - (optional) is a type of string
  scan_on_creation = null
  # scan_subdirectories - (optional) is a type of string
  scan_subdirectories = null
  # sensitivity - (optional) is a type of string
  sensitivity = null
  # server - (required) is a type of string
  server = null
  # server_type - (required) is a type of string
  server_type = null
  # tod_hour - (optional) is a type of number
  tod_hour = null
  # tod_min - (optional) is a type of number
  tod_min = null
  # username - (required) is a type of string
  username = null
  # vdom - (optional) is a type of string
  vdom = null
  # weekday - (optional) is a type of string
  weekday = null
}
```

[top](#index)

### Variables

```terraform
variable "date" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "file_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keep_modified" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remove_deleted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_on_creation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_subdirectories" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sensitivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(required)"
  type        = string
}

variable "server_type" {
  description = "(required)"
  type        = string
}

variable "tod_hour" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tod_min" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weekday" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dlp_fpdocsource" "this" {
  date                = var.date
  file_path           = var.file_path
  file_pattern        = var.file_pattern
  keep_modified       = var.keep_modified
  name                = var.name
  password            = var.password
  period              = var.period
  remove_deleted      = var.remove_deleted
  scan_on_creation    = var.scan_on_creation
  scan_subdirectories = var.scan_subdirectories
  sensitivity         = var.sensitivity
  server              = var.server
  server_type         = var.server_type
  tod_hour            = var.tod_hour
  tod_min             = var.tod_min
  username            = var.username
  vdom                = var.vdom
  weekday             = var.weekday
}
```

[top](#index)

### Outputs

```terraform
output "date" {
  description = "returns a number"
  value       = fortios_dlp_fpdocsource.this.date
}

output "file_path" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.file_path
}

output "file_pattern" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.file_pattern
}

output "id" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.id
}

output "keep_modified" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.keep_modified
}

output "name" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.name
}

output "period" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.period
}

output "remove_deleted" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.remove_deleted
}

output "scan_on_creation" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.scan_on_creation
}

output "scan_subdirectories" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.scan_subdirectories
}

output "sensitivity" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.sensitivity
}

output "tod_hour" {
  description = "returns a number"
  value       = fortios_dlp_fpdocsource.this.tod_hour
}

output "tod_min" {
  description = "returns a number"
  value       = fortios_dlp_fpdocsource.this.tod_min
}

output "vdom" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.vdom
}

output "weekday" {
  description = "returns a string"
  value       = fortios_dlp_fpdocsource.this.weekday
}

output "this" {
  value = fortios_dlp_fpdocsource.this
}
```

[top](#index)