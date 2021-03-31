# fortios_system_speedtestschedule

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
module "fortios_system_speedtestschedule" {
  source = "./modules/fortios/r/fortios_system_speedtestschedule"

  # diffserv - (optional) is a type of string
  diffserv = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # interface - (optional) is a type of string
  interface = null
  # server_name - (optional) is a type of string
  server_name = null
  # status - (optional) is a type of string
  status = null
  # update_inbandwidth - (optional) is a type of string
  update_inbandwidth = null
  # update_inbandwidth_maximum - (optional) is a type of number
  update_inbandwidth_maximum = null
  # update_inbandwidth_minimum - (optional) is a type of number
  update_inbandwidth_minimum = null
  # update_outbandwidth - (optional) is a type of string
  update_outbandwidth = null
  # update_outbandwidth_maximum - (optional) is a type of number
  update_outbandwidth_maximum = null
  # update_outbandwidth_minimum - (optional) is a type of number
  update_outbandwidth_minimum = null

  schedules = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "diffserv" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_inbandwidth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_inbandwidth_maximum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "update_inbandwidth_minimum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "update_outbandwidth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_outbandwidth_maximum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "update_outbandwidth_minimum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "schedules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_speedtestschedule" "this" {
  diffserv                    = var.diffserv
  dynamic_sort_subtable       = var.dynamic_sort_subtable
  interface                   = var.interface
  server_name                 = var.server_name
  status                      = var.status
  update_inbandwidth          = var.update_inbandwidth
  update_inbandwidth_maximum  = var.update_inbandwidth_maximum
  update_inbandwidth_minimum  = var.update_inbandwidth_minimum
  update_outbandwidth         = var.update_outbandwidth
  update_outbandwidth_maximum = var.update_outbandwidth_maximum
  update_outbandwidth_minimum = var.update_outbandwidth_minimum

  dynamic "schedules" {
    for_each = var.schedules
    content {
      name = schedules.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "diffserv" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.diffserv
}

output "id" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.interface
}

output "server_name" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.server_name
}

output "status" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.status
}

output "update_inbandwidth" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.update_inbandwidth
}

output "update_inbandwidth_maximum" {
  description = "returns a number"
  value       = fortios_system_speedtestschedule.this.update_inbandwidth_maximum
}

output "update_inbandwidth_minimum" {
  description = "returns a number"
  value       = fortios_system_speedtestschedule.this.update_inbandwidth_minimum
}

output "update_outbandwidth" {
  description = "returns a string"
  value       = fortios_system_speedtestschedule.this.update_outbandwidth
}

output "update_outbandwidth_maximum" {
  description = "returns a number"
  value       = fortios_system_speedtestschedule.this.update_outbandwidth_maximum
}

output "update_outbandwidth_minimum" {
  description = "returns a number"
  value       = fortios_system_speedtestschedule.this.update_outbandwidth_minimum
}

output "this" {
  value = fortios_system_speedtestschedule.this
}
```

[top](#index)