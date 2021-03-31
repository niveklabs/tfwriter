# fortios_user_tacacs

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
module "fortios_user_tacacs" {
  source = "./modules/fortios/r/fortios_user_tacacs"

  # authen_type - (optional) is a type of string
  authen_type = null
  # authorization - (optional) is a type of string
  authorization = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # key - (optional) is a type of string
  key = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # secondary_key - (optional) is a type of string
  secondary_key = null
  # secondary_server - (optional) is a type of string
  secondary_server = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # tertiary_key - (optional) is a type of string
  tertiary_key = null
  # tertiary_server - (optional) is a type of string
  tertiary_server = null
}
```

[top](#index)

### Variables

```terraform
variable "authen_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorization" {
  description = "(optional)"
  type        = string
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

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secondary_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_server" {
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

variable "tertiary_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tertiary_server" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_tacacs" "this" {
  authen_type             = var.authen_type
  authorization           = var.authorization
  interface               = var.interface
  interface_select_method = var.interface_select_method
  key                     = var.key
  name                    = var.name
  port                    = var.port
  secondary_key           = var.secondary_key
  secondary_server        = var.secondary_server
  server                  = var.server
  source_ip               = var.source_ip
  tertiary_key            = var.tertiary_key
  tertiary_server         = var.tertiary_server
}
```

[top](#index)

### Outputs

```terraform
output "authen_type" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.authen_type
}

output "authorization" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.authorization
}

output "id" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.interface_select_method
}

output "name" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_user_tacacs.this.port
}

output "secondary_server" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.secondary_server
}

output "server" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.source_ip
}

output "tertiary_server" {
  description = "returns a string"
  value       = fortios_user_tacacs.this.tertiary_server
}

output "this" {
  value = fortios_user_tacacs.this
}
```

[top](#index)