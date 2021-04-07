# panos_monitor_profile

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
module "panos_monitor_profile" {
  source = "./modules/panos/r/panos_monitor_profile"

  # action - (optional) is a type of string
  action = null
  # interval - (optional) is a type of number
  interval = null
  # name - (required) is a type of string
  name = null
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

variable "threshold" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_monitor_profile" "this" {
  # action - (optional) is a type of string
  action = var.action
  # interval - (optional) is a type of number
  interval = var.interval
  # name - (required) is a type of string
  name = var.name
  # threshold - (optional) is a type of number
  threshold = var.threshold
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_monitor_profile.this.id
}

output "this" {
  value = panos_monitor_profile.this
}
```

[top](#index)