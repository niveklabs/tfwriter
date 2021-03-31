# fortios_firewall_vip46

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
module "fortios_firewall_vip46" {
  source = "./modules/fortios/r/fortios_firewall_vip46"

  # arp_reply - (optional) is a type of string
  arp_reply = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # extip - (required) is a type of string
  extip = null
  # extport - (optional) is a type of string
  extport = null
  # fosid - (optional) is a type of number
  fosid = null
  # ldb_method - (optional) is a type of string
  ldb_method = null
  # mappedip - (required) is a type of string
  mappedip = null
  # mappedport - (optional) is a type of string
  mappedport = null
  # name - (optional) is a type of string
  name = null
  # portforward - (optional) is a type of string
  portforward = null
  # protocol - (optional) is a type of string
  protocol = null
  # server_type - (optional) is a type of string
  server_type = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  monitor = [{
    name = null
  }]

  realservers = [{
    client_ip         = null
    healthcheck       = null
    holddown_interval = null
    id                = null
    ip                = null
    max_connections   = null
    monitor           = null
    port              = null
    status            = null
    weight            = null
  }]

  src_filter = [{
    range = null
  }]

  srcintf_filter = [{
    interface_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "arp_reply" {
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

variable "extip" {
  description = "(required)"
  type        = string
}

variable "extport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ldb_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mappedip" {
  description = "(required)"
  type        = string
}

variable "mappedport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "portforward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "realservers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_ip         = string
      healthcheck       = string
      holddown_interval = number
      id                = number
      ip                = string
      max_connections   = number
      monitor           = string
      port              = number
      status            = string
      weight            = number
    }
  ))
  default = []
}

variable "src_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      range = string
    }
  ))
  default = []
}

variable "srcintf_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_vip46" "this" {
  arp_reply             = var.arp_reply
  color                 = var.color
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  extip                 = var.extip
  extport               = var.extport
  fosid                 = var.fosid
  ldb_method            = var.ldb_method
  mappedip              = var.mappedip
  mappedport            = var.mappedport
  name                  = var.name
  portforward           = var.portforward
  protocol              = var.protocol
  server_type           = var.server_type
  type                  = var.type
  uuid                  = var.uuid

  dynamic "monitor" {
    for_each = var.monitor
    content {
      name = monitor.value["name"]
    }
  }

  dynamic "realservers" {
    for_each = var.realservers
    content {
      client_ip         = realservers.value["client_ip"]
      healthcheck       = realservers.value["healthcheck"]
      holddown_interval = realservers.value["holddown_interval"]
      id                = realservers.value["id"]
      ip                = realservers.value["ip"]
      max_connections   = realservers.value["max_connections"]
      monitor           = realservers.value["monitor"]
      port              = realservers.value["port"]
      status            = realservers.value["status"]
      weight            = realservers.value["weight"]
    }
  }

  dynamic "src_filter" {
    for_each = var.src_filter
    content {
      range = src_filter.value["range"]
    }
  }

  dynamic "srcintf_filter" {
    for_each = var.srcintf_filter
    content {
      interface_name = srcintf_filter.value["interface_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arp_reply" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.arp_reply
}

output "color" {
  description = "returns a number"
  value       = fortios_firewall_vip46.this.color
}

output "extport" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.extport
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_vip46.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.id
}

output "ldb_method" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.ldb_method
}

output "mappedport" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.mappedport
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.name
}

output "portforward" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.portforward
}

output "protocol" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.protocol
}

output "server_type" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.server_type
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.type
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_vip46.this.uuid
}

output "this" {
  value = fortios_firewall_vip46.this
}
```

[top](#index)