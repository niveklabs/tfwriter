# fortios_dlp_settings

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
module "fortios_dlp_settings" {
  source = "./modules/fortios/r/fortios_dlp_settings"

  # cache_mem_percent - (optional) is a type of number
  cache_mem_percent = null
  # chunk_size - (optional) is a type of number
  chunk_size = null
  # db_mode - (optional) is a type of string
  db_mode = null
  # size - (optional) is a type of number
  size = null
  # storage_device - (optional) is a type of string
  storage_device = null
}
```

[top](#index)

### Variables

```terraform
variable "cache_mem_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "chunk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "db_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "storage_device" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dlp_settings" "this" {
  cache_mem_percent = var.cache_mem_percent
  chunk_size        = var.chunk_size
  db_mode           = var.db_mode
  size              = var.size
  storage_device    = var.storage_device
}
```

[top](#index)

### Outputs

```terraform
output "cache_mem_percent" {
  description = "returns a number"
  value       = fortios_dlp_settings.this.cache_mem_percent
}

output "chunk_size" {
  description = "returns a number"
  value       = fortios_dlp_settings.this.chunk_size
}

output "db_mode" {
  description = "returns a string"
  value       = fortios_dlp_settings.this.db_mode
}

output "id" {
  description = "returns a string"
  value       = fortios_dlp_settings.this.id
}

output "size" {
  description = "returns a number"
  value       = fortios_dlp_settings.this.size
}

output "storage_device" {
  description = "returns a string"
  value       = fortios_dlp_settings.this.storage_device
}

output "this" {
  value = fortios_dlp_settings.this
}
```

[top](#index)