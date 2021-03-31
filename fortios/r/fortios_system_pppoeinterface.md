# fortios_system_pppoeinterface

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
module "fortios_system_pppoeinterface" {
  source = "./modules/fortios/r/fortios_system_pppoeinterface"

  # ac_name - (optional) is a type of string
  ac_name = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # device - (required) is a type of string
  device = null
  # dial_on_demand - (optional) is a type of string
  dial_on_demand = null
  # disc_retry_timeout - (optional) is a type of number
  disc_retry_timeout = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # ipunnumbered - (optional) is a type of string
  ipunnumbered = null
  # ipv6 - (optional) is a type of string
  ipv6 = null
  # lcp_echo_interval - (optional) is a type of number
  lcp_echo_interval = null
  # lcp_max_echo_fails - (optional) is a type of number
  lcp_max_echo_fails = null
  # name - (optional) is a type of string
  name = null
  # padt_retry_timeout - (optional) is a type of number
  padt_retry_timeout = null
  # password - (optional) is a type of string
  password = null
  # pppoe_unnumbered_negotiate - (optional) is a type of string
  pppoe_unnumbered_negotiate = null
  # service_name - (optional) is a type of string
  service_name = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "ac_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device" {
  description = "(required)"
  type        = string
}

variable "dial_on_demand" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disc_retry_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipunnumbered" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lcp_echo_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lcp_max_echo_fails" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "padt_retry_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pppoe_unnumbered_negotiate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
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
resource "fortios_system_pppoeinterface" "this" {
  ac_name                    = var.ac_name
  auth_type                  = var.auth_type
  device                     = var.device
  dial_on_demand             = var.dial_on_demand
  disc_retry_timeout         = var.disc_retry_timeout
  idle_timeout               = var.idle_timeout
  ipunnumbered               = var.ipunnumbered
  ipv6                       = var.ipv6
  lcp_echo_interval          = var.lcp_echo_interval
  lcp_max_echo_fails         = var.lcp_max_echo_fails
  name                       = var.name
  padt_retry_timeout         = var.padt_retry_timeout
  password                   = var.password
  pppoe_unnumbered_negotiate = var.pppoe_unnumbered_negotiate
  service_name               = var.service_name
  username                   = var.username
}
```

[top](#index)

### Outputs

```terraform
output "ac_name" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.ac_name
}

output "auth_type" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.auth_type
}

output "dial_on_demand" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.dial_on_demand
}

output "disc_retry_timeout" {
  description = "returns a number"
  value       = fortios_system_pppoeinterface.this.disc_retry_timeout
}

output "id" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.id
}

output "idle_timeout" {
  description = "returns a number"
  value       = fortios_system_pppoeinterface.this.idle_timeout
}

output "ipunnumbered" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.ipunnumbered
}

output "ipv6" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.ipv6
}

output "lcp_echo_interval" {
  description = "returns a number"
  value       = fortios_system_pppoeinterface.this.lcp_echo_interval
}

output "lcp_max_echo_fails" {
  description = "returns a number"
  value       = fortios_system_pppoeinterface.this.lcp_max_echo_fails
}

output "name" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.name
}

output "padt_retry_timeout" {
  description = "returns a number"
  value       = fortios_system_pppoeinterface.this.padt_retry_timeout
}

output "pppoe_unnumbered_negotiate" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.pppoe_unnumbered_negotiate
}

output "service_name" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.service_name
}

output "username" {
  description = "returns a string"
  value       = fortios_system_pppoeinterface.this.username
}

output "this" {
  value = fortios_system_pppoeinterface.this
}
```

[top](#index)