# logicmonitor_device

[back](../logicmonitor.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    logicmonitor = ">= 1.3.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "logicmonitor_device" {
  source = "./modules/logicmonitor/r/logicmonitor_device"

  # collector - (required) is a type of number
  collector = null
  # description - (optional) is a type of string
  description = null
  # disable_alerting - (optional) is a type of bool
  disable_alerting = null
  # display_name - (optional) is a type of string
  display_name = null
  # hostgroup_id - (optional) is a type of string
  hostgroup_id = null
  # ip_addr - (required) is a type of string
  ip_addr = null
  # properties - (optional) is a type of map of string
  properties = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "collector" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_alerting" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostgroup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_addr" {
  description = "(required)"
  type        = string
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "logicmonitor_device" "this" {
  collector        = var.collector
  description      = var.description
  disable_alerting = var.disable_alerting
  display_name     = var.display_name
  hostgroup_id     = var.hostgroup_id
  ip_addr          = var.ip_addr
  properties       = var.properties
  type             = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = logicmonitor_device.this.id
}

output "this" {
  value = logicmonitor_device.this
}
```

[top](#index)