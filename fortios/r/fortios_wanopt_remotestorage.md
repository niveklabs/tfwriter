# fortios_wanopt_remotestorage

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
module "fortios_wanopt_remotestorage" {
  source = "./modules/fortios/r/fortios_wanopt_remotestorage"

  # local_cache_id - (optional) is a type of string
  local_cache_id = null
  # remote_cache_id - (optional) is a type of string
  remote_cache_id = null
  # remote_cache_ip - (optional) is a type of string
  remote_cache_ip = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "local_cache_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_cache_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_cache_ip" {
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
resource "fortios_wanopt_remotestorage" "this" {
  local_cache_id  = var.local_cache_id
  remote_cache_id = var.remote_cache_id
  remote_cache_ip = var.remote_cache_ip
  status          = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wanopt_remotestorage.this.id
}

output "local_cache_id" {
  description = "returns a string"
  value       = fortios_wanopt_remotestorage.this.local_cache_id
}

output "remote_cache_id" {
  description = "returns a string"
  value       = fortios_wanopt_remotestorage.this.remote_cache_id
}

output "remote_cache_ip" {
  description = "returns a string"
  value       = fortios_wanopt_remotestorage.this.remote_cache_ip
}

output "status" {
  description = "returns a string"
  value       = fortios_wanopt_remotestorage.this.status
}

output "this" {
  value = fortios_wanopt_remotestorage.this
}
```

[top](#index)