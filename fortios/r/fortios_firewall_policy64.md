# fortios_firewall_policy64

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
module "fortios_firewall_policy64" {
  source = "./modules/fortios/r/fortios_firewall_policy64"

  # action - (optional) is a type of string
  action = null
  # comments - (optional) is a type of string
  comments = null
  # dstintf - (required) is a type of string
  dstintf = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fixedport - (optional) is a type of string
  fixedport = null
  # ippool - (optional) is a type of string
  ippool = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = null
  # name - (optional) is a type of string
  name = null
  # per_ip_shaper - (optional) is a type of string
  per_ip_shaper = null
  # permit_any_host - (optional) is a type of string
  permit_any_host = null
  # policyid - (optional) is a type of number
  policyid = null
  # schedule - (required) is a type of string
  schedule = null
  # srcintf - (required) is a type of string
  srcintf = null
  # status - (optional) is a type of string
  status = null
  # tcp_mss_receiver - (optional) is a type of number
  tcp_mss_receiver = null
  # tcp_mss_sender - (optional) is a type of number
  tcp_mss_sender = null
  # traffic_shaper - (optional) is a type of string
  traffic_shaper = null
  # traffic_shaper_reverse - (optional) is a type of string
  traffic_shaper_reverse = null
  # uuid - (optional) is a type of string
  uuid = null

  dstaddr = [{
    name = null
  }]

  poolname = [{
    name = null
  }]

  service = [{
    name = null
  }]

  srcaddr = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dstintf" {
  description = "(required)"
  type        = string
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fixedport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ippool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logtraffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logtraffic_start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_ip_shaper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permit_any_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policyid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "schedule" {
  description = "(required)"
  type        = string
}

variable "srcintf" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_mss_receiver" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_mss_sender" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_shaper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_shaper_reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dstaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "poolname" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_policy64" "this" {
  action                 = var.action
  comments               = var.comments
  dstintf                = var.dstintf
  dynamic_sort_subtable  = var.dynamic_sort_subtable
  fixedport              = var.fixedport
  ippool                 = var.ippool
  logtraffic             = var.logtraffic
  logtraffic_start       = var.logtraffic_start
  name                   = var.name
  per_ip_shaper          = var.per_ip_shaper
  permit_any_host        = var.permit_any_host
  policyid               = var.policyid
  schedule               = var.schedule
  srcintf                = var.srcintf
  status                 = var.status
  tcp_mss_receiver       = var.tcp_mss_receiver
  tcp_mss_sender         = var.tcp_mss_sender
  traffic_shaper         = var.traffic_shaper
  traffic_shaper_reverse = var.traffic_shaper_reverse
  uuid                   = var.uuid

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
    }
  }

  dynamic "poolname" {
    for_each = var.poolname
    content {
      name = poolname.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      name = service.value["name"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      name = srcaddr.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.action
}

output "fixedport" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.fixedport
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.id
}

output "ippool" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.ippool
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.name
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.per_ip_shaper
}

output "permit_any_host" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.permit_any_host
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_policy64.this.policyid
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = fortios_firewall_policy64.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = fortios_firewall_policy64.this.tcp_mss_sender
}

output "traffic_shaper" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.traffic_shaper_reverse
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_policy64.this.uuid
}

output "this" {
  value = fortios_firewall_policy64.this
}
```

[top](#index)