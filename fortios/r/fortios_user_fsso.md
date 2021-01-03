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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_fsso" {
  source = "./modules/fortios/r/fortios_user_fsso"

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
  # port - (required) is a type of number
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
}
```

[top](#index)

### Variables

```terraform
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
  description = "(required)"
  type        = number
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
```

[top](#index)

### Resource

```terraform
resource "fortios_user_fsso" "this" {
  ldap_server = var.ldap_server
  name        = var.name
  password    = var.password
  password2   = var.password2
  password3   = var.password3
  password4   = var.password4
  password5   = var.password5
  port        = var.port
  port2       = var.port2
  port3       = var.port3
  port4       = var.port4
  port5       = var.port5
  server      = var.server
  server2     = var.server2
  server3     = var.server3
  server4     = var.server4
  server5     = var.server5
  source_ip   = var.source_ip
  source_ip6  = var.source_ip6
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_user_fsso.this.id
}

output "ldap_server" {
  description = "returns a string"
  value       = fortios_user_fsso.this.ldap_server
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

output "this" {
  value = fortios_user_fsso.this
}
```

[top](#index)