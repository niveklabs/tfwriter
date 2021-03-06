# panos_panorama_bfd_profile

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
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_bfd_profile" {
  source = "./modules/panos/r/panos_panorama_bfd_profile"

  # detection_multiplier - (optional) is a type of number
  detection_multiplier = null
  # hold_time - (optional) is a type of number
  hold_time = null
  # minimum_rx_interval - (optional) is a type of number
  minimum_rx_interval = null
  # minimum_rx_ttl - (optional) is a type of number
  minimum_rx_ttl = null
  # minimum_tx_interval - (optional) is a type of number
  minimum_tx_interval = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
}
```

[top](#index)

### Variables

```terraform
variable "detection_multiplier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hold_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minimum_rx_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minimum_rx_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minimum_tx_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_bfd_profile" "this" {
  # detection_multiplier - (optional) is a type of number
  detection_multiplier = var.detection_multiplier
  # hold_time - (optional) is a type of number
  hold_time = var.hold_time
  # minimum_rx_interval - (optional) is a type of number
  minimum_rx_interval = var.minimum_rx_interval
  # minimum_rx_ttl - (optional) is a type of number
  minimum_rx_ttl = var.minimum_rx_ttl
  # minimum_tx_interval - (optional) is a type of number
  minimum_tx_interval = var.minimum_tx_interval
  # mode - (optional) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # template - (optional) is a type of string
  template = var.template
  # template_stack - (optional) is a type of string
  template_stack = var.template_stack
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_bfd_profile.this.id
}

output "this" {
  value = panos_panorama_bfd_profile.this
}
```

[top](#index)