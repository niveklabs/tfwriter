# fortios_system_emailserver

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
module "fortios_system_emailserver" {
  source = "./modules/fortios/r/fortios_system_emailserver"

  # authenticate - (optional) is a type of string
  authenticate = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # reply_to - (optional) is a type of string
  reply_to = null
  # security - (optional) is a type of string
  security = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_ip6 - (optional) is a type of string
  source_ip6 = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # type - (optional) is a type of string
  type = null
  # username - (optional) is a type of string
  username = null
  # validate_server - (optional) is a type of string
  validate_server = null
}
```

[top](#index)

### Variables

```terraform
variable "authenticate" {
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

variable "reply_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
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

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "validate_server" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_emailserver" "this" {
  authenticate          = var.authenticate
  password              = var.password
  port                  = var.port
  reply_to              = var.reply_to
  security              = var.security
  server                = var.server
  source_ip             = var.source_ip
  source_ip6            = var.source_ip6
  ssl_min_proto_version = var.ssl_min_proto_version
  type                  = var.type
  username              = var.username
  validate_server       = var.validate_server
}
```

[top](#index)

### Outputs

```terraform
output "authenticate" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.authenticate
}

output "id" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.id
}

output "port" {
  description = "returns a number"
  value       = fortios_system_emailserver.this.port
}

output "reply_to" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.reply_to
}

output "security" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.security
}

output "server" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.source_ip6
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.ssl_min_proto_version
}

output "type" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.type
}

output "username" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.username
}

output "validate_server" {
  description = "returns a string"
  value       = fortios_system_emailserver.this.validate_server
}

output "this" {
  value = fortios_system_emailserver.this
}
```

[top](#index)