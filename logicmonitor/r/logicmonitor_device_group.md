# logicmonitor_device_group

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
module "logicmonitor_device_group" {
  source = "./modules/logicmonitor/r/logicmonitor_device_group"

  # applies_to - (optional) is a type of string
  applies_to = null
  # description - (optional) is a type of string
  description = null
  # disable_alerting - (optional) is a type of bool
  disable_alerting = null
  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of number
  parent_id = null
  # properties - (optional) is a type of map of string
  properties = {}
}
```

[top](#index)

### Variables

```terraform
variable "applies_to" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "logicmonitor_device_group" "this" {
  # applies_to - (optional) is a type of string
  applies_to = var.applies_to
  # description - (optional) is a type of string
  description = var.description
  # disable_alerting - (optional) is a type of bool
  disable_alerting = var.disable_alerting
  # name - (required) is a type of string
  name = var.name
  # parent_id - (optional) is a type of number
  parent_id = var.parent_id
  # properties - (optional) is a type of map of string
  properties = var.properties
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = logicmonitor_device_group.this.id
}

output "this" {
  value = logicmonitor_device_group.this
}
```

[top](#index)