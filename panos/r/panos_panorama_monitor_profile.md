# panos_panorama_monitor_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_monitor_profile" {
  source = "./modules/panos/r/panos_panorama_monitor_profile"

  # action - (optional) is a type of string
  action = null
  # interval - (optional) is a type of number
  interval = null
  # name - (required) is a type of string
  name = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # threshold - (optional) is a type of number
  threshold = null
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

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_monitor_profile" "this" {
  action         = var.action
  interval       = var.interval
  name           = var.name
  template       = var.template
  template_stack = var.template_stack
  threshold      = var.threshold
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_monitor_profile.this.id
}

output "this" {
  value = panos_panorama_monitor_profile.this
}
```

[top](#index)