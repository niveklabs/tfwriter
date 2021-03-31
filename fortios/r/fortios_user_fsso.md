# fortios_user_fsso

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
module "fortios_user_fsso" {
  source = "./modules/fortios/r/fortios_user_fsso"

  # group_poll_interval - (optional) is a type of number
  group_poll_interval = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # ldap_poll - (optional) is a type of string
  ldap_poll = null
  # ldap_poll_filter - (optional) is a type of string
  ldap_poll_filter = null
  # ldap_poll_interval - (optional) is a type of number
  ldap_poll_interval = null
  # ldap_server - (optional) is a type of string
  ldap_server = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # password2 - (optional) is a type of string
  password2 = null
  # password3 - (optional) is a type of string
  password3 = null
  # password4 - (optional) is a type of string
  password4 = null
  # password5 - (optional) is a type of string
  password5 = null
  # port - (optional) is a type of number
  port = null
  # port2 - (optional) is a type of number
  port2 = null
  # port3 - (optional) is a type of number
  port3 = null
  # port4 - (optional) is a type of number
  port4 = null
  # port5 - (optional) is a type of number
  port5 = null
  # server - (required) is a type of string
  server = null
  # server2 - (optional) is a type of string
  server2 = null
  # server3 - (optional) is a type of string
  server3 = null
  # server4 - (optional) is a type of string
  server4 = null
  # server5 - (optional) is a type of string
  server5 = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_ip6 - (optional) is a type of string
  source_ip6 = null
  # ssl - (optional) is a type of string
  ssl = null
  # ssl_trusted_cert - (optional) is a type of string
  ssl_trusted_cert = null
  # type - (optional) is a type of string
  type = null
  # user_info_server - (optional) is a type of string
  user_info_server = null
}
```

[top](#index)

### Variables

```terraform
variable "group_poll_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_poll" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_poll_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_poll_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ldap_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port3" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port4" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port5" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server" {
  description = "(required)"
  type        = string
}

variable "server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_trusted_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_info_server" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_fsso" "this" {
  group_poll_interval     = var.group_poll_interval
  interface               = var.interface
  interface_select_method = var.interface_select_method
  ldap_poll               = var.ldap_poll
  ldap_poll_filter        = var.ldap_poll_filter
  ldap_poll_interval      = var.ldap_poll_interval
  ldap_server             = var.ldap_server
  name                    = var.name
  password                = var.password
  password2               = var.password2
  password3               = var.password3
  password4               = var.password4
  password5               = var.password5
  port                    = var.port
  port2                   = var.port2
  port3                   = var.port3
  port4                   = var.port4
  port5                   = var.port5
  server                  = var.server
  server2                 = var.server2
  server3                 = var.server3
  server4                 = var.server4
  server5                 = var.server5
  source_ip               = var.source_ip
  source_ip6              = var.source_ip6
  ssl                     = var.ssl
  ssl_trusted_cert        = var.ssl_trusted_cert
  type                    = var.type
  user_info_server        = var.user_info_server
}
```

[top](#index)

### Outputs

```terraform
output "group_poll_interval" {
  description = "returns a number"
  value       = fortios_user_fsso.this.group_poll_interval
}

output "id" {
  description = "returns a string"
  value       = fortios_user_fsso.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_user_fsso.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_user_fsso.this.interface_select_method
}

output "ldap_poll" {
  description = "returns a string"
  value       = fortios_user_fsso.this.ldap_poll
}

output "ldap_poll_filter" {
  description = "returns a string"
  value       = fortios_user_fsso.this.ldap_poll_filter
}

output "ldap_poll_interval" {
  description = "returns a number"
  value       = fortios_user_fsso.this.ldap_poll_interval
}

output "ldap_server" {
  description = "returns a string"
  value       = fortios_user_fsso.this.ldap_server
}

output "port" {
  description = "returns a number"
  value       = fortios_user_fsso.this.port
}

output "port2" {
  description = "returns a number"
  value       = fortios_user_fsso.this.port2
}

output "port3" {
  description = "returns a number"
  value       = fortios_user_fsso.this.port3
}

output "port4" {
  description = "returns a number"
  value       = fortios_user_fsso.this.port4
}

output "port5" {
  description = "returns a number"
  value       = fortios_user_fsso.this.port5
}

output "server2" {
  description = "returns a string"
  value       = fortios_user_fsso.this.server2
}

output "server3" {
  description = "returns a string"
  value       = fortios_user_fsso.this.server3
}

output "server4" {
  description = "returns a string"
  value       = fortios_user_fsso.this.server4
}

output "server5" {
  description = "returns a string"
  value       = fortios_user_fsso.this.server5
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_user_fsso.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = fortios_user_fsso.this.source_ip6
}

output "ssl" {
  description = "returns a string"
  value       = fortios_user_fsso.this.ssl
}

output "ssl_trusted_cert" {
  description = "returns a string"
  value       = fortios_user_fsso.this.ssl_trusted_cert
}

output "type" {
  description = "returns a string"
  value       = fortios_user_fsso.this.type
}

output "user_info_server" {
  description = "returns a string"
  value       = fortios_user_fsso.this.user_info_server
}

output "this" {
  value = fortios_user_fsso.this
}
```

[top](#index)