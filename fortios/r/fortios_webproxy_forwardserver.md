# fortios_webproxy_forwardserver

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
module "fortios_webproxy_forwardserver" {
  source = "./modules/fortios/r/fortios_webproxy_forwardserver"

  # addr_type - (optional) is a type of string
  addr_type = null
  # comment - (optional) is a type of string
  comment = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # healthcheck - (optional) is a type of string
  healthcheck = null
  # ip - (optional) is a type of string
  ip = null
  # monitor - (optional) is a type of string
  monitor = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # server_down_option - (optional) is a type of string
  server_down_option = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "addr_type" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "healthcheck" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_down_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webproxy_forwardserver" "this" {
  # addr_type - (optional) is a type of string
  addr_type = var.addr_type
  # comment - (optional) is a type of string
  comment = var.comment
  # fqdn - (optional) is a type of string
  fqdn = var.fqdn
  # healthcheck - (optional) is a type of string
  healthcheck = var.healthcheck
  # ip - (optional) is a type of string
  ip = var.ip
  # monitor - (optional) is a type of string
  monitor = var.monitor
  # name - (optional) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # port - (optional) is a type of number
  port = var.port
  # server_down_option - (optional) is a type of string
  server_down_option = var.server_down_option
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "addr_type" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.addr_type
}

output "comment" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.comment
}

output "fqdn" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.fqdn
}

output "healthcheck" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.healthcheck
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.ip
}

output "monitor" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.monitor
}

output "name" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_webproxy_forwardserver.this.port
}

output "server_down_option" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.server_down_option
}

output "username" {
  description = "returns a string"
  value       = fortios_webproxy_forwardserver.this.username
}

output "this" {
  value = fortios_webproxy_forwardserver.this
}
```

[top](#index)