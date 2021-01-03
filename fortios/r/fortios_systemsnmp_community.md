# fortios_systemsnmp_community

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
module "fortios_systemsnmp_community" {
  source = "./modules/fortios/r/fortios_systemsnmp_community"

  # events - (optional) is a type of string
  events = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null
  # query_v1_port - (optional) is a type of number
  query_v1_port = null
  # query_v1_status - (optional) is a type of string
  query_v1_status = null
  # query_v2c_port - (optional) is a type of number
  query_v2c_port = null
  # query_v2c_status - (optional) is a type of string
  query_v2c_status = null
  # status - (optional) is a type of string
  status = null
  # trap_v1_lport - (optional) is a type of number
  trap_v1_lport = null
  # trap_v1_rport - (optional) is a type of number
  trap_v1_rport = null
  # trap_v1_status - (optional) is a type of string
  trap_v1_status = null
  # trap_v2c_lport - (optional) is a type of number
  trap_v2c_lport = null
  # trap_v2c_rport - (optional) is a type of number
  trap_v2c_rport = null
  # trap_v2c_status - (optional) is a type of string
  trap_v2c_status = null

  hosts = [{
    ha_direct = null
    host_type = null
    id        = null
    ip        = null
    source_ip = null
  }]

  hosts6 = [{
    ha_direct   = null
    host_type   = null
    id          = null
    ipv6        = null
    source_ipv6 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "events" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query_v1_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query_v1_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_v2c_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query_v2c_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trap_v1_lport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_v1_rport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_v1_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trap_v2c_lport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_v2c_rport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_v2c_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hosts" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ha_direct = string
      host_type = string
      id        = number
      ip        = string
      source_ip = string
    }
  ))
  default = []
}

variable "hosts6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ha_direct   = string
      host_type   = string
      id          = number
      ipv6        = string
      source_ipv6 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemsnmp_community" "this" {
  events           = var.events
  fosid            = var.fosid
  name             = var.name
  query_v1_port    = var.query_v1_port
  query_v1_status  = var.query_v1_status
  query_v2c_port   = var.query_v2c_port
  query_v2c_status = var.query_v2c_status
  status           = var.status
  trap_v1_lport    = var.trap_v1_lport
  trap_v1_rport    = var.trap_v1_rport
  trap_v1_status   = var.trap_v1_status
  trap_v2c_lport   = var.trap_v2c_lport
  trap_v2c_rport   = var.trap_v2c_rport
  trap_v2c_status  = var.trap_v2c_status

  dynamic "hosts" {
    for_each = var.hosts
    content {
      ha_direct = hosts.value["ha_direct"]
      host_type = hosts.value["host_type"]
      id        = hosts.value["id"]
      ip        = hosts.value["ip"]
      source_ip = hosts.value["source_ip"]
    }
  }

  dynamic "hosts6" {
    for_each = var.hosts6
    content {
      ha_direct   = hosts6.value["ha_direct"]
      host_type   = hosts6.value["host_type"]
      id          = hosts6.value["id"]
      ipv6        = hosts6.value["ipv6"]
      source_ipv6 = hosts6.value["source_ipv6"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "events" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.events
}

output "id" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.id
}

output "query_v1_port" {
  description = "returns a number"
  value       = fortios_systemsnmp_community.this.query_v1_port
}

output "query_v1_status" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.query_v1_status
}

output "query_v2c_port" {
  description = "returns a number"
  value       = fortios_systemsnmp_community.this.query_v2c_port
}

output "query_v2c_status" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.query_v2c_status
}

output "status" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.status
}

output "trap_v1_lport" {
  description = "returns a number"
  value       = fortios_systemsnmp_community.this.trap_v1_lport
}

output "trap_v1_rport" {
  description = "returns a number"
  value       = fortios_systemsnmp_community.this.trap_v1_rport
}

output "trap_v1_status" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.trap_v1_status
}

output "trap_v2c_lport" {
  description = "returns a number"
  value       = fortios_systemsnmp_community.this.trap_v2c_lport
}

output "trap_v2c_rport" {
  description = "returns a number"
  value       = fortios_systemsnmp_community.this.trap_v2c_rport
}

output "trap_v2c_status" {
  description = "returns a string"
  value       = fortios_systemsnmp_community.this.trap_v2c_status
}

output "this" {
  value = fortios_systemsnmp_community.this
}
```

[top](#index)