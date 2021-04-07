# fortios_system_mobiletunnel

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
module "fortios_system_mobiletunnel" {
  source = "./modules/fortios/r/fortios_system_mobiletunnel"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # hash_algorithm - (required) is a type of string
  hash_algorithm = null
  # home_address - (optional) is a type of string
  home_address = null
  # home_agent - (required) is a type of string
  home_agent = null
  # lifetime - (required) is a type of number
  lifetime = null
  # n_mhae_key - (optional) is a type of string
  n_mhae_key = null
  # n_mhae_key_type - (required) is a type of string
  n_mhae_key_type = null
  # n_mhae_spi - (required) is a type of number
  n_mhae_spi = null
  # name - (optional) is a type of string
  name = null
  # reg_interval - (required) is a type of number
  reg_interval = null
  # reg_retry - (required) is a type of number
  reg_retry = null
  # renew_interval - (required) is a type of number
  renew_interval = null
  # roaming_interface - (required) is a type of string
  roaming_interface = null
  # status - (optional) is a type of string
  status = null
  # tunnel_mode - (required) is a type of string
  tunnel_mode = null

  network = [{
    id        = null
    interface = null
    prefix    = null
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

variable "hash_algorithm" {
  description = "(required)"
  type        = string
}

variable "home_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "home_agent" {
  description = "(required)"
  type        = string
}

variable "lifetime" {
  description = "(required)"
  type        = number
}

variable "n_mhae_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "n_mhae_key_type" {
  description = "(required)"
  type        = string
}

variable "n_mhae_spi" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reg_interval" {
  description = "(required)"
  type        = number
}

variable "reg_retry" {
  description = "(required)"
  type        = number
}

variable "renew_interval" {
  description = "(required)"
  type        = number
}

variable "roaming_interface" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_mode" {
  description = "(required)"
  type        = string
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id        = number
      interface = string
      prefix    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_mobiletunnel" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # hash_algorithm - (required) is a type of string
  hash_algorithm = var.hash_algorithm
  # home_address - (optional) is a type of string
  home_address = var.home_address
  # home_agent - (required) is a type of string
  home_agent = var.home_agent
  # lifetime - (required) is a type of number
  lifetime = var.lifetime
  # n_mhae_key - (optional) is a type of string
  n_mhae_key = var.n_mhae_key
  # n_mhae_key_type - (required) is a type of string
  n_mhae_key_type = var.n_mhae_key_type
  # n_mhae_spi - (required) is a type of number
  n_mhae_spi = var.n_mhae_spi
  # name - (optional) is a type of string
  name = var.name
  # reg_interval - (required) is a type of number
  reg_interval = var.reg_interval
  # reg_retry - (required) is a type of number
  reg_retry = var.reg_retry
  # renew_interval - (required) is a type of number
  renew_interval = var.renew_interval
  # roaming_interface - (required) is a type of string
  roaming_interface = var.roaming_interface
  # status - (optional) is a type of string
  status = var.status
  # tunnel_mode - (required) is a type of string
  tunnel_mode = var.tunnel_mode

  dynamic "network" {
    for_each = var.network
    content {
      # id - (optional) is a type of number
      id = network.value["id"]
      # interface - (optional) is a type of string
      interface = network.value["interface"]
      # prefix - (optional) is a type of string
      prefix = network.value["prefix"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "home_address" {
  description = "returns a string"
  value       = fortios_system_mobiletunnel.this.home_address
}

output "id" {
  description = "returns a string"
  value       = fortios_system_mobiletunnel.this.id
}

output "n_mhae_key" {
  description = "returns a string"
  value       = fortios_system_mobiletunnel.this.n_mhae_key
  sensitive   = true
}

output "name" {
  description = "returns a string"
  value       = fortios_system_mobiletunnel.this.name
}

output "status" {
  description = "returns a string"
  value       = fortios_system_mobiletunnel.this.status
}

output "this" {
  value = fortios_system_mobiletunnel.this
}
```

[top](#index)