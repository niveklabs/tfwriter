# fortios_system_linkmonitor

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
module "fortios_system_linkmonitor" {
  source = "./modules/fortios/r/fortios_system_linkmonitor"

  # addr_mode - (optional) is a type of string
  addr_mode = null
  # failtime - (optional) is a type of number
  failtime = null
  # gateway_ip - (optional) is a type of string
  gateway_ip = null
  # gateway_ip6 - (optional) is a type of string
  gateway_ip6 = null
  # ha_priority - (optional) is a type of number
  ha_priority = null
  # http_agent - (optional) is a type of string
  http_agent = null
  # http_get - (optional) is a type of string
  http_get = null
  # http_match - (optional) is a type of string
  http_match = null
  # interval - (optional) is a type of number
  interval = null
  # name - (optional) is a type of string
  name = null
  # packet_size - (optional) is a type of number
  packet_size = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # recoverytime - (optional) is a type of number
  recoverytime = null
  # security_mode - (optional) is a type of string
  security_mode = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_ip6 - (optional) is a type of string
  source_ip6 = null
  # srcintf - (optional) is a type of string
  srcintf = null
  # status - (optional) is a type of string
  status = null
  # update_cascade_interface - (optional) is a type of string
  update_cascade_interface = null
  # update_static_route - (optional) is a type of string
  update_static_route = null

  server = [{
    address = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "addr_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "failtime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gateway_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_agent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_get" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "packet_size" {
  description = "(optional)"
  type        = number
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

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recoverytime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_mode" {
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

variable "srcintf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_cascade_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_static_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      address = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_linkmonitor" "this" {
  addr_mode                = var.addr_mode
  failtime                 = var.failtime
  gateway_ip               = var.gateway_ip
  gateway_ip6              = var.gateway_ip6
  ha_priority              = var.ha_priority
  http_agent               = var.http_agent
  http_get                 = var.http_get
  http_match               = var.http_match
  interval                 = var.interval
  name                     = var.name
  packet_size              = var.packet_size
  password                 = var.password
  port                     = var.port
  protocol                 = var.protocol
  recoverytime             = var.recoverytime
  security_mode            = var.security_mode
  source_ip                = var.source_ip
  source_ip6               = var.source_ip6
  srcintf                  = var.srcintf
  status                   = var.status
  update_cascade_interface = var.update_cascade_interface
  update_static_route      = var.update_static_route

  dynamic "server" {
    for_each = var.server
    content {
      address = server.value["address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "addr_mode" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.addr_mode
}

output "failtime" {
  description = "returns a number"
  value       = fortios_system_linkmonitor.this.failtime
}

output "gateway_ip" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.gateway_ip
}

output "gateway_ip6" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.gateway_ip6
}

output "ha_priority" {
  description = "returns a number"
  value       = fortios_system_linkmonitor.this.ha_priority
}

output "http_agent" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.http_agent
}

output "http_get" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.http_get
}

output "http_match" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.http_match
}

output "id" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.id
}

output "interval" {
  description = "returns a number"
  value       = fortios_system_linkmonitor.this.interval
}

output "name" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.name
}

output "packet_size" {
  description = "returns a number"
  value       = fortios_system_linkmonitor.this.packet_size
}

output "port" {
  description = "returns a number"
  value       = fortios_system_linkmonitor.this.port
}

output "protocol" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.protocol
}

output "recoverytime" {
  description = "returns a number"
  value       = fortios_system_linkmonitor.this.recoverytime
}

output "security_mode" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.security_mode
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.source_ip6
}

output "srcintf" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.srcintf
}

output "status" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.status
}

output "update_cascade_interface" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.update_cascade_interface
}

output "update_static_route" {
  description = "returns a string"
  value       = fortios_system_linkmonitor.this.update_static_route
}

output "this" {
  value = fortios_system_linkmonitor.this
}
```

[top](#index)