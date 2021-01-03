# bigip_ltm_profile_fastl4

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
module "bigip_ltm_profile_fastl4" {
  source = "./modules/bigip/r/bigip_ltm_profile_fastl4"

  # client_timeout - (optional) is a type of number
  client_timeout = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # explicitflow_migration - (optional) is a type of string
  explicitflow_migration = null
  # hardware_syncookie - (optional) is a type of string
  hardware_syncookie = null
  # idle_timeout - (optional) is a type of string
  idle_timeout = null
  # iptos_toclient - (optional) is a type of string
  iptos_toclient = null
  # iptos_toserver - (optional) is a type of string
  iptos_toserver = null
  # keepalive_interval - (optional) is a type of string
  keepalive_interval = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "client_timeout" {
  description = "(optional) - Number of seconds allowed for a client to transmit enough data to select a server when you have late binding enabled. Value -1 means indefinite (not recommended)"
  type        = number
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Use the parent Fastl4 profile"
  type        = string
  default     = null
}

variable "explicitflow_migration" {
  description = "(optional) - Use the parent Fastl4 profile"
  type        = string
  default     = null
}

variable "hardware_syncookie" {
  description = "(optional) - Use the parent Fastl4 profile"
  type        = string
  default     = null
}

variable "idle_timeout" {
  description = "(optional) - Number of seconds (default 300; may not be 0) connection may remain idle before it becomes eligible for deletion. Value -1 (not recommended) means infinite"
  type        = string
  default     = null
}

variable "iptos_toclient" {
  description = "(optional) - Use the parent Fastl4 profile"
  type        = string
  default     = null
}

variable "iptos_toserver" {
  description = "(optional) - Use the parent Fastl4 profile"
  type        = string
  default     = null
}

variable "keepalive_interval" {
  description = "(optional) - Use the parent Fastl4 profile"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the Fastl4 Profile"
  type        = string
}

variable "partition" {
  description = "(optional) - name of partition"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_fastl4" "this" {
  client_timeout         = var.client_timeout
  defaults_from          = var.defaults_from
  explicitflow_migration = var.explicitflow_migration
  hardware_syncookie     = var.hardware_syncookie
  idle_timeout           = var.idle_timeout
  iptos_toclient         = var.iptos_toclient
  iptos_toserver         = var.iptos_toserver
  keepalive_interval     = var.keepalive_interval
  name                   = var.name
  partition              = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "client_timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_fastl4.this.client_timeout
}

output "defaults_from" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.defaults_from
}

output "explicitflow_migration" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.explicitflow_migration
}

output "hardware_syncookie" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.hardware_syncookie
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.id
}

output "idle_timeout" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.idle_timeout
}

output "iptos_toclient" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.iptos_toclient
}

output "iptos_toserver" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.iptos_toserver
}

output "keepalive_interval" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.keepalive_interval
}

output "partition" {
  description = "returns a string"
  value       = bigip_ltm_profile_fastl4.this.partition
}

output "this" {
  value = bigip_ltm_profile_fastl4.this
}
```

[top](#index)