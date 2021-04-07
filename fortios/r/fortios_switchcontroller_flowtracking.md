# fortios_switchcontroller_flowtracking

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
module "fortios_switchcontroller_flowtracking" {
  source = "./modules/fortios/r/fortios_switchcontroller_flowtracking"

  # collector_ip - (optional) is a type of string
  collector_ip = null
  # collector_port - (optional) is a type of number
  collector_port = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # format - (optional) is a type of string
  format = null
  # level - (optional) is a type of string
  level = null
  # max_export_pkt_size - (optional) is a type of number
  max_export_pkt_size = null
  # sample_mode - (optional) is a type of string
  sample_mode = null
  # sample_rate - (optional) is a type of number
  sample_rate = null
  # timeout_general - (optional) is a type of number
  timeout_general = null
  # timeout_icmp - (optional) is a type of number
  timeout_icmp = null
  # timeout_max - (optional) is a type of number
  timeout_max = null
  # timeout_tcp - (optional) is a type of number
  timeout_tcp = null
  # timeout_tcp_fin - (optional) is a type of number
  timeout_tcp_fin = null
  # timeout_tcp_rst - (optional) is a type of number
  timeout_tcp_rst = null
  # timeout_udp - (optional) is a type of number
  timeout_udp = null
  # transport - (optional) is a type of string
  transport = null

  aggregates = [{
    id = null
    ip = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "collector_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "collector_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_export_pkt_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sample_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sample_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_general" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_icmp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_tcp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_tcp_fin" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_tcp_rst" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout_udp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "transport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aggregates" {
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
resource "fortios_switchcontroller_flowtracking" "this" {
  # collector_ip - (optional) is a type of string
  collector_ip = var.collector_ip
  # collector_port - (optional) is a type of number
  collector_port = var.collector_port
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # format - (optional) is a type of string
  format = var.format
  # level - (optional) is a type of string
  level = var.level
  # max_export_pkt_size - (optional) is a type of number
  max_export_pkt_size = var.max_export_pkt_size
  # sample_mode - (optional) is a type of string
  sample_mode = var.sample_mode
  # sample_rate - (optional) is a type of number
  sample_rate = var.sample_rate
  # timeout_general - (optional) is a type of number
  timeout_general = var.timeout_general
  # timeout_icmp - (optional) is a type of number
  timeout_icmp = var.timeout_icmp
  # timeout_max - (optional) is a type of number
  timeout_max = var.timeout_max
  # timeout_tcp - (optional) is a type of number
  timeout_tcp = var.timeout_tcp
  # timeout_tcp_fin - (optional) is a type of number
  timeout_tcp_fin = var.timeout_tcp_fin
  # timeout_tcp_rst - (optional) is a type of number
  timeout_tcp_rst = var.timeout_tcp_rst
  # timeout_udp - (optional) is a type of number
  timeout_udp = var.timeout_udp
  # transport - (optional) is a type of string
  transport = var.transport

  dynamic "aggregates" {
    for_each = var.aggregates
    content {
      # id - (optional) is a type of number
      id = aggregates.value["id"]
      # ip - (optional) is a type of string
      ip = aggregates.value["ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "collector_ip" {
  description = "returns a string"
  value       = fortios_switchcontroller_flowtracking.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.collector_port
}

output "format" {
  description = "returns a string"
  value       = fortios_switchcontroller_flowtracking.this.format
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_flowtracking.this.id
}

output "level" {
  description = "returns a string"
  value       = fortios_switchcontroller_flowtracking.this.level
}

output "max_export_pkt_size" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.max_export_pkt_size
}

output "sample_mode" {
  description = "returns a string"
  value       = fortios_switchcontroller_flowtracking.this.sample_mode
}

output "sample_rate" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.sample_rate
}

output "timeout_general" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_general
}

output "timeout_icmp" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_icmp
}

output "timeout_max" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_max
}

output "timeout_tcp" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_tcp
}

output "timeout_tcp_fin" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_tcp_fin
}

output "timeout_tcp_rst" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_tcp_rst
}

output "timeout_udp" {
  description = "returns a number"
  value       = fortios_switchcontroller_flowtracking.this.timeout_udp
}

output "transport" {
  description = "returns a string"
  value       = fortios_switchcontroller_flowtracking.this.transport
}

output "this" {
  value = fortios_switchcontroller_flowtracking.this
}
```

[top](#index)