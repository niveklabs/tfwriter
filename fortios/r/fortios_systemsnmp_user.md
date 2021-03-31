# fortios_systemsnmp_user

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
module "fortios_systemsnmp_user" {
  source = "./modules/fortios/r/fortios_systemsnmp_user"

  # auth_proto - (optional) is a type of string
  auth_proto = null
  # auth_pwd - (optional) is a type of string
  auth_pwd = null
  # events - (optional) is a type of string
  events = null
  # ha_direct - (optional) is a type of string
  ha_direct = null
  # name - (required) is a type of string
  name = null
  # notify_hosts - (optional) is a type of string
  notify_hosts = null
  # notify_hosts6 - (optional) is a type of string
  notify_hosts6 = null
  # priv_proto - (optional) is a type of string
  priv_proto = null
  # priv_pwd - (optional) is a type of string
  priv_pwd = null
  # queries - (optional) is a type of string
  queries = null
  # query_port - (optional) is a type of number
  query_port = null
  # security_level - (optional) is a type of string
  security_level = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_ipv6 - (optional) is a type of string
  source_ipv6 = null
  # status - (optional) is a type of string
  status = null
  # trap_lport - (optional) is a type of number
  trap_lport = null
  # trap_rport - (optional) is a type of number
  trap_rport = null
  # trap_status - (optional) is a type of string
  trap_status = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "events" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_direct" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notify_hosts" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notify_hosts6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priv_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priv_pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "queries" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trap_lport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_rport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemsnmp_user" "this" {
  auth_proto     = var.auth_proto
  auth_pwd       = var.auth_pwd
  events         = var.events
  ha_direct      = var.ha_direct
  name           = var.name
  notify_hosts   = var.notify_hosts
  notify_hosts6  = var.notify_hosts6
  priv_proto     = var.priv_proto
  priv_pwd       = var.priv_pwd
  queries        = var.queries
  query_port     = var.query_port
  security_level = var.security_level
  source_ip      = var.source_ip
  source_ipv6    = var.source_ipv6
  status         = var.status
  trap_lport     = var.trap_lport
  trap_rport     = var.trap_rport
  trap_status    = var.trap_status
}
```

[top](#index)

### Outputs

```terraform
output "auth_proto" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.auth_proto
}

output "events" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.events
}

output "ha_direct" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.ha_direct
}

output "id" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.id
}

output "notify_hosts" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.notify_hosts
}

output "notify_hosts6" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.notify_hosts6
}

output "priv_proto" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.priv_proto
}

output "queries" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.queries
}

output "query_port" {
  description = "returns a number"
  value       = fortios_systemsnmp_user.this.query_port
}

output "security_level" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.security_level
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.source_ip
}

output "source_ipv6" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.source_ipv6
}

output "status" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.status
}

output "trap_lport" {
  description = "returns a number"
  value       = fortios_systemsnmp_user.this.trap_lport
}

output "trap_rport" {
  description = "returns a number"
  value       = fortios_systemsnmp_user.this.trap_rport
}

output "trap_status" {
  description = "returns a string"
  value       = fortios_systemsnmp_user.this.trap_status
}

output "this" {
  value = fortios_systemsnmp_user.this
}
```

[top](#index)