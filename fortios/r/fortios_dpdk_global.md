# fortios_dpdk_global

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
module "fortios_dpdk_global" {
  source = "./modules/fortios/r/fortios_dpdk_global"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # elasticbuffer - (optional) is a type of string
  elasticbuffer = null
  # hugepage_percentage - (optional) is a type of number
  hugepage_percentage = null
  # mbufpool_percentage - (optional) is a type of number
  mbufpool_percentage = null
  # multiqueue - (optional) is a type of string
  multiqueue = null
  # per_session_accounting - (optional) is a type of string
  per_session_accounting = null
  # sleep_on_idle - (optional) is a type of string
  sleep_on_idle = null
  # status - (optional) is a type of string
  status = null

  interface = [{
    interface_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elasticbuffer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hugepage_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mbufpool_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "multiqueue" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_session_accounting" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sleep_on_idle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dpdk_global" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # elasticbuffer - (optional) is a type of string
  elasticbuffer = var.elasticbuffer
  # hugepage_percentage - (optional) is a type of number
  hugepage_percentage = var.hugepage_percentage
  # mbufpool_percentage - (optional) is a type of number
  mbufpool_percentage = var.mbufpool_percentage
  # multiqueue - (optional) is a type of string
  multiqueue = var.multiqueue
  # per_session_accounting - (optional) is a type of string
  per_session_accounting = var.per_session_accounting
  # sleep_on_idle - (optional) is a type of string
  sleep_on_idle = var.sleep_on_idle
  # status - (optional) is a type of string
  status = var.status

  dynamic "interface" {
    for_each = var.interface
    content {
      # interface_name - (optional) is a type of string
      interface_name = interface.value["interface_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "elasticbuffer" {
  description = "returns a string"
  value       = fortios_dpdk_global.this.elasticbuffer
}

output "hugepage_percentage" {
  description = "returns a number"
  value       = fortios_dpdk_global.this.hugepage_percentage
}

output "id" {
  description = "returns a string"
  value       = fortios_dpdk_global.this.id
}

output "mbufpool_percentage" {
  description = "returns a number"
  value       = fortios_dpdk_global.this.mbufpool_percentage
}

output "multiqueue" {
  description = "returns a string"
  value       = fortios_dpdk_global.this.multiqueue
}

output "per_session_accounting" {
  description = "returns a string"
  value       = fortios_dpdk_global.this.per_session_accounting
}

output "sleep_on_idle" {
  description = "returns a string"
  value       = fortios_dpdk_global.this.sleep_on_idle
}

output "status" {
  description = "returns a string"
  value       = fortios_dpdk_global.this.status
}

output "this" {
  value = fortios_dpdk_global.this
}
```

[top](#index)