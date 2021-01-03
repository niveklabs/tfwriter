# bigip_ltm_profile_oneconnect

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_profile_oneconnect" {
  source = "./modules/bigip/r/bigip_ltm_profile_oneconnect"

  # defaults_from - (optional) is a type of string
  defaults_from = null
  # idle_timeout_override - (optional) is a type of string
  idle_timeout_override = null
  # limit_type - (optional) is a type of string
  limit_type = null
  # max_age - (optional) is a type of number
  max_age = null
  # max_reuse - (optional) is a type of number
  max_reuse = null
  # max_size - (optional) is a type of number
  max_size = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
  # share_pools - (optional) is a type of string
  share_pools = null
  # source_mask - (optional) is a type of string
  source_mask = null
}
```

[top](#index)

### Variables

```terraform
variable "defaults_from" {
  description = "(optional) - Use the parent oneconnect profile"
  type        = string
  default     = null
}

variable "idle_timeout_override" {
  description = "(optional) - idleTimeoutOverride can be enabled or disabled"
  type        = string
  default     = null
}

variable "limit_type" {
  description = "(optional) - Controls how connection limits are enforced in conjunction with OneConnect. The default is None. Supported Values: [None,idle,strict]"
  type        = string
  default     = null
}

variable "max_age" {
  description = "(optional) - max_age has integer value typical 3600 sec"
  type        = number
  default     = null
}

variable "max_reuse" {
  description = "(optional) - max_reuse has integer value typical 1000 sec"
  type        = number
  default     = null
}

variable "max_size" {
  description = "(optional) - max_size has integer value typical 1000 sec"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the Oneconnect Profile"
  type        = string
}

variable "partition" {
  description = "(optional) - name of partition"
  type        = string
  default     = null
}

variable "share_pools" {
  description = "(optional) - sharePools can be enabled or disabled"
  type        = string
  default     = null
}

variable "source_mask" {
  description = "(optional) - source_mask can be 255.255.255.255"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_oneconnect" "this" {
  defaults_from         = var.defaults_from
  idle_timeout_override = var.idle_timeout_override
  limit_type            = var.limit_type
  max_age               = var.max_age
  max_reuse             = var.max_reuse
  max_size              = var.max_size
  name                  = var.name
  partition             = var.partition
  share_pools           = var.share_pools
  source_mask           = var.source_mask
}
```

[top](#index)

### Outputs

```terraform
output "defaults_from" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.defaults_from
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.id
}

output "idle_timeout_override" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.idle_timeout_override
}

output "limit_type" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.limit_type
}

output "max_age" {
  description = "returns a number"
  value       = bigip_ltm_profile_oneconnect.this.max_age
}

output "max_reuse" {
  description = "returns a number"
  value       = bigip_ltm_profile_oneconnect.this.max_reuse
}

output "max_size" {
  description = "returns a number"
  value       = bigip_ltm_profile_oneconnect.this.max_size
}

output "partition" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.partition
}

output "share_pools" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.share_pools
}

output "source_mask" {
  description = "returns a string"
  value       = bigip_ltm_profile_oneconnect.this.source_mask
}

output "this" {
  value = bigip_ltm_profile_oneconnect.this
}
```

[top](#index)