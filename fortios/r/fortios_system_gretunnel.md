# fortios_system_gretunnel

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
module "fortios_system_gretunnel" {
  source = "./modules/fortios/r/fortios_system_gretunnel"

  # checksum_reception - (optional) is a type of string
  checksum_reception = null
  # checksum_transmission - (optional) is a type of string
  checksum_transmission = null
  # diffservcode - (optional) is a type of string
  diffservcode = null
  # dscp_copying - (optional) is a type of string
  dscp_copying = null
  # interface - (optional) is a type of string
  interface = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # keepalive_failtimes - (optional) is a type of number
  keepalive_failtimes = null
  # keepalive_interval - (optional) is a type of number
  keepalive_interval = null
  # key_inbound - (optional) is a type of number
  key_inbound = null
  # key_outbound - (optional) is a type of number
  key_outbound = null
  # local_gw - (required) is a type of string
  local_gw = null
  # local_gw6 - (optional) is a type of string
  local_gw6 = null
  # name - (optional) is a type of string
  name = null
  # remote_gw - (required) is a type of string
  remote_gw = null
  # remote_gw6 - (optional) is a type of string
  remote_gw6 = null
  # sequence_number_reception - (optional) is a type of string
  sequence_number_reception = null
  # sequence_number_transmission - (optional) is a type of string
  sequence_number_transmission = null
}
```

[top](#index)

### Variables

```terraform
variable "checksum_reception" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "checksum_transmission" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dscp_copying" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keepalive_failtimes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keepalive_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "key_inbound" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "key_outbound" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_gw" {
  description = "(required)"
  type        = string
}

variable "local_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_gw" {
  description = "(required)"
  type        = string
}

variable "remote_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sequence_number_reception" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sequence_number_transmission" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_gretunnel" "this" {
  checksum_reception           = var.checksum_reception
  checksum_transmission        = var.checksum_transmission
  diffservcode                 = var.diffservcode
  dscp_copying                 = var.dscp_copying
  interface                    = var.interface
  ip_version                   = var.ip_version
  keepalive_failtimes          = var.keepalive_failtimes
  keepalive_interval           = var.keepalive_interval
  key_inbound                  = var.key_inbound
  key_outbound                 = var.key_outbound
  local_gw                     = var.local_gw
  local_gw6                    = var.local_gw6
  name                         = var.name
  remote_gw                    = var.remote_gw
  remote_gw6                   = var.remote_gw6
  sequence_number_reception    = var.sequence_number_reception
  sequence_number_transmission = var.sequence_number_transmission
}
```

[top](#index)

### Outputs

```terraform
output "checksum_reception" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.checksum_reception
}

output "checksum_transmission" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.checksum_transmission
}

output "diffservcode" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.diffservcode
}

output "dscp_copying" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.dscp_copying
}

output "id" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.interface
}

output "ip_version" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.ip_version
}

output "keepalive_failtimes" {
  description = "returns a number"
  value       = fortios_system_gretunnel.this.keepalive_failtimes
}

output "keepalive_interval" {
  description = "returns a number"
  value       = fortios_system_gretunnel.this.keepalive_interval
}

output "key_inbound" {
  description = "returns a number"
  value       = fortios_system_gretunnel.this.key_inbound
}

output "key_outbound" {
  description = "returns a number"
  value       = fortios_system_gretunnel.this.key_outbound
}

output "local_gw6" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.local_gw6
}

output "name" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.name
}

output "remote_gw6" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.remote_gw6
}

output "sequence_number_reception" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.sequence_number_reception
}

output "sequence_number_transmission" {
  description = "returns a string"
  value       = fortios_system_gretunnel.this.sequence_number_transmission
}

output "this" {
  value = fortios_system_gretunnel.this
}
```

[top](#index)