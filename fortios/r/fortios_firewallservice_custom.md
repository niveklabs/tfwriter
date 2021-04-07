# fortios_firewallservice_custom

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
module "fortios_firewallservice_custom" {
  source = "./modules/fortios/r/fortios_firewallservice_custom"

  # app_service_type - (optional) is a type of string
  app_service_type = null
  # category - (optional) is a type of string
  category = null
  # check_reset_range - (optional) is a type of string
  check_reset_range = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # helper - (optional) is a type of string
  helper = null
  # icmpcode - (optional) is a type of number
  icmpcode = null
  # icmptype - (optional) is a type of number
  icmptype = null
  # iprange - (optional) is a type of string
  iprange = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # protocol_number - (optional) is a type of number
  protocol_number = null
  # proxy - (optional) is a type of string
  proxy = null
  # sctp_portrange - (optional) is a type of string
  sctp_portrange = null
  # session_ttl - (optional) is a type of number
  session_ttl = null
  # tcp_halfclose_timer - (optional) is a type of number
  tcp_halfclose_timer = null
  # tcp_halfopen_timer - (optional) is a type of number
  tcp_halfopen_timer = null
  # tcp_portrange - (optional) is a type of string
  tcp_portrange = null
  # tcp_timewait_timer - (optional) is a type of number
  tcp_timewait_timer = null
  # udp_idle_timer - (optional) is a type of number
  udp_idle_timer = null
  # udp_portrange - (optional) is a type of string
  udp_portrange = null
  # visibility - (optional) is a type of string
  visibility = null

  app_category = [{
    id = null
  }]

  application = [{
    id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_service_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_reset_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "helper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmpcode" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmptype" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iprange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy" {
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
  type        = number
  default     = null
}

variable "tcp_halfclose_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_halfopen_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_portrange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_timewait_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "udp_idle_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "udp_portrange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "application" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallservice_custom" "this" {
  # app_service_type - (optional) is a type of string
  app_service_type = var.app_service_type
  # category - (optional) is a type of string
  category = var.category
  # check_reset_range - (optional) is a type of string
  check_reset_range = var.check_reset_range
  # color - (optional) is a type of number
  color = var.color
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fqdn - (optional) is a type of string
  fqdn = var.fqdn
  # helper - (optional) is a type of string
  helper = var.helper
  # icmpcode - (optional) is a type of number
  icmpcode = var.icmpcode
  # icmptype - (optional) is a type of number
  icmptype = var.icmptype
  # iprange - (optional) is a type of string
  iprange = var.iprange
  # name - (optional) is a type of string
  name = var.name
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # protocol_number - (optional) is a type of number
  protocol_number = var.protocol_number
  # proxy - (optional) is a type of string
  proxy = var.proxy
  # sctp_portrange - (optional) is a type of string
  sctp_portrange = var.sctp_portrange
  # session_ttl - (optional) is a type of number
  session_ttl = var.session_ttl
  # tcp_halfclose_timer - (optional) is a type of number
  tcp_halfclose_timer = var.tcp_halfclose_timer
  # tcp_halfopen_timer - (optional) is a type of number
  tcp_halfopen_timer = var.tcp_halfopen_timer
  # tcp_portrange - (optional) is a type of string
  tcp_portrange = var.tcp_portrange
  # tcp_timewait_timer - (optional) is a type of number
  tcp_timewait_timer = var.tcp_timewait_timer
  # udp_idle_timer - (optional) is a type of number
  udp_idle_timer = var.udp_idle_timer
  # udp_portrange - (optional) is a type of string
  udp_portrange = var.udp_portrange
  # visibility - (optional) is a type of string
  visibility = var.visibility

  dynamic "app_category" {
    for_each = var.app_category
    content {
      # id - (optional) is a type of number
      id = app_category.value["id"]
    }
  }

  dynamic "application" {
    for_each = var.application
    content {
      # id - (optional) is a type of number
      id = application.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_service_type" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.app_service_type
}

output "category" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.category
}

output "check_reset_range" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.check_reset_range
}

output "color" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.color
}

output "fqdn" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.fqdn
}

output "helper" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.helper
}

output "icmpcode" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.icmpcode
}

output "icmptype" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.icmptype
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.id
}

output "iprange" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.iprange
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.name
}

output "protocol" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.protocol
}

output "protocol_number" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.protocol_number
}

output "proxy" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.proxy
}

output "sctp_portrange" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.sctp_portrange
}

output "session_ttl" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.session_ttl
}

output "tcp_halfclose_timer" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.tcp_halfclose_timer
}

output "tcp_halfopen_timer" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.tcp_halfopen_timer
}

output "tcp_portrange" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.tcp_portrange
}

output "tcp_timewait_timer" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.tcp_timewait_timer
}

output "udp_idle_timer" {
  description = "returns a number"
  value       = fortios_firewallservice_custom.this.udp_idle_timer
}

output "udp_portrange" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.udp_portrange
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewallservice_custom.this.visibility
}

output "this" {
  value = fortios_firewallservice_custom.this
}
```

[top](#index)