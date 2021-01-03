# fortios_log_eventfilter

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
module "fortios_log_eventfilter" {
  source = "./modules/fortios/r/fortios_log_eventfilter"

  # compliance_check - (optional) is a type of string
  compliance_check = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # event - (optional) is a type of string
  event = null
  # ha - (optional) is a type of string
  ha = null
  # router - (optional) is a type of string
  router = null
  # security_rating - (optional) is a type of string
  security_rating = null
  # system - (optional) is a type of string
  system = null
  # user - (optional) is a type of string
  user = null
  # vpn - (optional) is a type of string
  vpn = null
  # wan_opt - (optional) is a type of string
  wan_opt = null
  # wireless_activity - (optional) is a type of string
  wireless_activity = null
}
```

[top](#index)

### Variables

```terraform
variable "compliance_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_rating" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wan_opt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wireless_activity" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_eventfilter" "this" {
  compliance_check  = var.compliance_check
  endpoint          = var.endpoint
  event             = var.event
  ha                = var.ha
  router            = var.router
  security_rating   = var.security_rating
  system            = var.system
  user              = var.user
  vpn               = var.vpn
  wan_opt           = var.wan_opt
  wireless_activity = var.wireless_activity
}
```

[top](#index)

### Outputs

```terraform
output "compliance_check" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.compliance_check
}

output "endpoint" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.endpoint
}

output "event" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.event
}

output "ha" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.ha
}

output "id" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.id
}

output "router" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.router
}

output "security_rating" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.security_rating
}

output "system" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.system
}

output "user" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.user
}

output "vpn" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.vpn
}

output "wan_opt" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.wan_opt
}

output "wireless_activity" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.wireless_activity
}

output "this" {
  value = fortios_log_eventfilter.this
}
```

[top](#index)