# fortios_firewall_object_service

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
module "fortios_firewall_object_service" {
  source = "./modules/fortios/r/fortios_firewall_object_service"

  # category - (required) is a type of string
  category = null
  # comment - (optional) is a type of string
  comment = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # icmpcode - (optional) is a type of string
  icmpcode = null
  # icmptype - (optional) is a type of string
  icmptype = null
  # iprange - (optional) is a type of string
  iprange = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
  # protocol_number - (optional) is a type of string
  protocol_number = null
  # sctp_portrange - (optional) is a type of string
  sctp_portrange = null
  # session_ttl - (optional) is a type of string
  session_ttl = null
  # tcp_portrange - (optional) is a type of string
  tcp_portrange = null
  # udp_portrange - (optional) is a type of string
  udp_portrange = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(required)"
  type        = string
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmpcode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmptype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iprange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "protocol_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sctp_portrange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_ttl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_portrange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "udp_portrange" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_object_service" "this" {
  category        = var.category
  comment         = var.comment
  fqdn            = var.fqdn
  icmpcode        = var.icmpcode
  icmptype        = var.icmptype
  iprange         = var.iprange
  name            = var.name
  protocol        = var.protocol
  protocol_number = var.protocol_number
  sctp_portrange  = var.sctp_portrange
  session_ttl     = var.session_ttl
  tcp_portrange   = var.tcp_portrange
  udp_portrange   = var.udp_portrange
}
```

[top](#index)

### Outputs

```terraform
output "fqdn" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.fqdn
}

output "icmpcode" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.icmpcode
}

output "icmptype" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.icmptype
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.id
}

output "iprange" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.iprange
}

output "protocol_number" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.protocol_number
}

output "sctp_portrange" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.sctp_portrange
}

output "session_ttl" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.session_ttl
}

output "tcp_portrange" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.tcp_portrange
}

output "udp_portrange" {
  description = "returns a string"
  value       = fortios_firewall_object_service.this.udp_portrange
}

output "this" {
  value = fortios_firewall_object_service.this
}
```

[top](#index)