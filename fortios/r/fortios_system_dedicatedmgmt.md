# fortios_system_dedicatedmgmt

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
module "fortios_system_dedicatedmgmt" {
  source = "./modules/fortios/r/fortios_system_dedicatedmgmt"

  # default_gateway - (optional) is a type of string
  default_gateway = null
  # dhcp_end_ip - (optional) is a type of string
  dhcp_end_ip = null
  # dhcp_netmask - (optional) is a type of string
  dhcp_netmask = null
  # dhcp_server - (optional) is a type of string
  dhcp_server = null
  # dhcp_start_ip - (optional) is a type of string
  dhcp_start_ip = null
  # interface - (optional) is a type of string
  interface = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "default_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
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
resource "fortios_system_dedicatedmgmt" "this" {
  default_gateway = var.default_gateway
  dhcp_end_ip     = var.dhcp_end_ip
  dhcp_netmask    = var.dhcp_netmask
  dhcp_server     = var.dhcp_server
  dhcp_start_ip   = var.dhcp_start_ip
  interface       = var.interface
  status          = var.status
}
```

[top](#index)

### Outputs

```terraform
output "default_gateway" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.default_gateway
}

output "dhcp_end_ip" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.dhcp_end_ip
}

output "dhcp_netmask" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.dhcp_netmask
}

output "dhcp_server" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.dhcp_server
}

output "dhcp_start_ip" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.dhcp_start_ip
}

output "id" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.interface
}

output "status" {
  description = "returns a string"
  value       = fortios_system_dedicatedmgmt.this.status
}

output "this" {
  value = fortios_system_dedicatedmgmt.this
}
```

[top](#index)