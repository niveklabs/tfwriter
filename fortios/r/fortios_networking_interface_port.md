# fortios_networking_interface_port

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
module "fortios_networking_interface_port" {
  source = "./modules/fortios/r/fortios_networking_interface_port"

  # alias - (optional) is a type of string
  alias = null
  # allowaccess - (optional) is a type of string
  allowaccess = null
  # defaultgw - (optional) is a type of string
  defaultgw = null
  # description - (optional) is a type of string
  description = null
  # device_identification - (optional) is a type of string
  device_identification = null
  # distance - (optional) is a type of string
  distance = null
  # dns_server_override - (optional) is a type of string
  dns_server_override = null
  # interface - (optional) is a type of string
  interface = null
  # ip - (optional) is a type of string
  ip = null
  # mode - (optional) is a type of string
  mode = null
  # mtu - (optional) is a type of string
  mtu = null
  # mtu_override - (optional) is a type of string
  mtu_override = null
  # name - (required) is a type of string
  name = null
  # role - (optional) is a type of string
  role = null
  # speed - (optional) is a type of string
  speed = null
  # status - (optional) is a type of string
  status = null
  # tcp_mss - (optional) is a type of string
  tcp_mss = null
  # type - (required) is a type of string
  type = null
  # vdom - (optional) is a type of string
  vdom = null
  # vlanid - (optional) is a type of string
  vlanid = null
}
```

[top](#index)

### Variables

```terraform
variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defaultgw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_identification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mtu_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "speed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_mss" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlanid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_networking_interface_port" "this" {
  # alias - (optional) is a type of string
  alias = var.alias
  # allowaccess - (optional) is a type of string
  allowaccess = var.allowaccess
  # defaultgw - (optional) is a type of string
  defaultgw = var.defaultgw
  # description - (optional) is a type of string
  description = var.description
  # device_identification - (optional) is a type of string
  device_identification = var.device_identification
  # distance - (optional) is a type of string
  distance = var.distance
  # dns_server_override - (optional) is a type of string
  dns_server_override = var.dns_server_override
  # interface - (optional) is a type of string
  interface = var.interface
  # ip - (optional) is a type of string
  ip = var.ip
  # mode - (optional) is a type of string
  mode = var.mode
  # mtu - (optional) is a type of string
  mtu = var.mtu
  # mtu_override - (optional) is a type of string
  mtu_override = var.mtu_override
  # name - (required) is a type of string
  name = var.name
  # role - (optional) is a type of string
  role = var.role
  # speed - (optional) is a type of string
  speed = var.speed
  # status - (optional) is a type of string
  status = var.status
  # tcp_mss - (optional) is a type of string
  tcp_mss = var.tcp_mss
  # type - (required) is a type of string
  type = var.type
  # vdom - (optional) is a type of string
  vdom = var.vdom
  # vlanid - (optional) is a type of string
  vlanid = var.vlanid
}
```

[top](#index)

### Outputs

```terraform
output "alias" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.alias
}

output "allowaccess" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.allowaccess
}

output "defaultgw" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.defaultgw
}

output "device_identification" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.device_identification
}

output "distance" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.distance
}

output "dns_server_override" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.dns_server_override
}

output "id" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.interface
}

output "ip" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.ip
}

output "mode" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.mode
}

output "mtu" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.mtu
}

output "mtu_override" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.mtu_override
}

output "role" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.role
}

output "speed" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.speed
}

output "status" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.status
}

output "tcp_mss" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.tcp_mss
}

output "vdom" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.vdom
}

output "vlanid" {
  description = "returns a string"
  value       = fortios_networking_interface_port.this.vlanid
}

output "this" {
  value = fortios_networking_interface_port.this
}
```

[top](#index)