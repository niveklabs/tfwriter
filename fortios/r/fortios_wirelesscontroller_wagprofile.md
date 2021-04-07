# fortios_wirelesscontroller_wagprofile

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
module "fortios_wirelesscontroller_wagprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_wagprofile"

  # comment - (optional) is a type of string
  comment = null
  # dhcp_ip_addr - (optional) is a type of string
  dhcp_ip_addr = null
  # name - (optional) is a type of string
  name = null
  # ping_interval - (optional) is a type of number
  ping_interval = null
  # ping_number - (optional) is a type of number
  ping_number = null
  # return_packet_timeout - (optional) is a type of number
  return_packet_timeout = null
  # tunnel_type - (optional) is a type of string
  tunnel_type = null
  # wag_ip - (optional) is a type of string
  wag_ip = null
  # wag_port - (optional) is a type of number
  wag_port = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_ip_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ping_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ping_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "return_packet_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tunnel_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wag_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wag_port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_wagprofile" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # dhcp_ip_addr - (optional) is a type of string
  dhcp_ip_addr = var.dhcp_ip_addr
  # name - (optional) is a type of string
  name = var.name
  # ping_interval - (optional) is a type of number
  ping_interval = var.ping_interval
  # ping_number - (optional) is a type of number
  ping_number = var.ping_number
  # return_packet_timeout - (optional) is a type of number
  return_packet_timeout = var.return_packet_timeout
  # tunnel_type - (optional) is a type of string
  tunnel_type = var.tunnel_type
  # wag_ip - (optional) is a type of string
  wag_ip = var.wag_ip
  # wag_port - (optional) is a type of number
  wag_port = var.wag_port
}
```

[top](#index)

### Outputs

```terraform
output "dhcp_ip_addr" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wagprofile.this.dhcp_ip_addr
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wagprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wagprofile.this.name
}

output "ping_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wagprofile.this.ping_interval
}

output "ping_number" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wagprofile.this.ping_number
}

output "return_packet_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wagprofile.this.return_packet_timeout
}

output "tunnel_type" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wagprofile.this.tunnel_type
}

output "wag_ip" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wagprofile.this.wag_ip
}

output "wag_port" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_wagprofile.this.wag_port
}

output "this" {
  value = fortios_wirelesscontroller_wagprofile.this
}
```

[top](#index)