# fortios_switchcontroller_snmpcommunity

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
module "fortios_switchcontroller_snmpcommunity" {
  source = "./modules/fortios/r/fortios_switchcontroller_snmpcommunity"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # events - (optional) is a type of string
  events = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
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
    id = null
    ip = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "events" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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
      id = number
      ip = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_snmpcommunity" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  events                = var.events
  fosid                 = var.fosid
  name                  = var.name
  query_v1_port         = var.query_v1_port
  query_v1_status       = var.query_v1_status
  query_v2c_port        = var.query_v2c_port
  query_v2c_status      = var.query_v2c_status
  status                = var.status
  trap_v1_lport         = var.trap_v1_lport
  trap_v1_rport         = var.trap_v1_rport
  trap_v1_status        = var.trap_v1_status
  trap_v2c_lport        = var.trap_v2c_lport
  trap_v2c_rport        = var.trap_v2c_rport
  trap_v2c_status       = var.trap_v2c_status

  dynamic "hosts" {
    for_each = var.hosts
    content {
      id = hosts.value["id"]
      ip = hosts.value["ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "events" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.events
}

output "fosid" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.name
}

output "query_v1_port" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.query_v1_port
}

output "query_v1_status" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.query_v1_status
}

output "query_v2c_port" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.query_v2c_port
}

output "query_v2c_status" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.query_v2c_status
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.status
}

output "trap_v1_lport" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.trap_v1_lport
}

output "trap_v1_rport" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.trap_v1_rport
}

output "trap_v1_status" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.trap_v1_status
}

output "trap_v2c_lport" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.trap_v2c_lport
}

output "trap_v2c_rport" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpcommunity.this.trap_v2c_rport
}

output "trap_v2c_status" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpcommunity.this.trap_v2c_status
}

output "this" {
  value = fortios_switchcontroller_snmpcommunity.this
}
```

[top](#index)