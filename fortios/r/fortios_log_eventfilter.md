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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_log_eventfilter" {
  source = "./modules/fortios/r/fortios_log_eventfilter"

  # cifs - (optional) is a type of string
  cifs = null
  # compliance_check - (optional) is a type of string
  compliance_check = null
  # connector - (optional) is a type of string
  connector = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # event - (optional) is a type of string
  event = null
  # fortiextender - (optional) is a type of string
  fortiextender = null
  # ha - (optional) is a type of string
  ha = null
  # router - (optional) is a type of string
  router = null
  # sdwan - (optional) is a type of string
  sdwan = null
  # security_rating - (optional) is a type of string
  security_rating = null
  # switch_controller - (optional) is a type of string
  switch_controller = null
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
variable "cifs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compliance_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connector" {
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

variable "fortiextender" {
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

variable "sdwan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_rating" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_controller" {
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
  cifs              = var.cifs
  compliance_check  = var.compliance_check
  connector         = var.connector
  endpoint          = var.endpoint
  event             = var.event
  fortiextender     = var.fortiextender
  ha                = var.ha
  router            = var.router
  sdwan             = var.sdwan
  security_rating   = var.security_rating
  switch_controller = var.switch_controller
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
output "cifs" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.cifs
}

output "compliance_check" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.compliance_check
}

output "connector" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.connector
}

output "endpoint" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.endpoint
}

output "event" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.event
}

output "fortiextender" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.fortiextender
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

output "sdwan" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.sdwan
}

output "security_rating" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.security_rating
}

output "switch_controller" {
  description = "returns a string"
  value       = fortios_log_eventfilter.this.switch_controller
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