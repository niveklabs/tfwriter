# nsxt_lb_icmp_monitor

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_lb_icmp_monitor" {
  source = "./modules/nsxt/r/nsxt_lb_icmp_monitor"

  # data_length - (optional) is a type of number
  data_length = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # fall_count - (optional) is a type of number
  fall_count = null
  # interval - (optional) is a type of number
  interval = null
  # monitor_port - (optional) is a type of string
  monitor_port = null
  # rise_count - (optional) is a type of number
  rise_count = null
  # timeout - (optional) is a type of number
  timeout = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data_length" {
  description = "(optional) - The data size (in bytes) of the ICMP healthcheck packet"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "fall_count" {
  description = "(optional) - Number of consecutive checks that must fail before marking it down"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional) - The frequency at which the system issues the monitor check (in seconds)"
  type        = number
  default     = null
}

variable "monitor_port" {
  description = "(optional) - If the monitor port is specified, it would override pool member port setting for healthcheck. A port range is not supported"
  type        = string
  default     = null
}

variable "rise_count" {
  description = "(optional) - Number of consecutive checks that must pass before marking it up"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional) - Number of seconds the target has to respond to the monitor request"
  type        = number
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_lb_icmp_monitor" "this" {
  # data_length - (optional) is a type of number
  data_length = var.data_length
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # fall_count - (optional) is a type of number
  fall_count = var.fall_count
  # interval - (optional) is a type of number
  interval = var.interval
  # monitor_port - (optional) is a type of string
  monitor_port = var.monitor_port
  # rise_count - (optional) is a type of number
  rise_count = var.rise_count
  # timeout - (optional) is a type of number
  timeout = var.timeout

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_icmp_monitor.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_icmp_monitor.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_icmp_monitor.this.revision
}

output "this" {
  value = nsxt_lb_icmp_monitor.this
}
```

[top](#index)