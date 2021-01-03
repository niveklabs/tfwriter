# pagerduty_maintenance_window

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_maintenance_window" {
  source = "./modules/pagerduty/r/pagerduty_maintenance_window"

  # description - (optional) is a type of string
  description = null
  # end_time - (required) is a type of string
  end_time = null
  # services - (required) is a type of set of string
  services = []
  # start_time - (required) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_time" {
  description = "(required)"
  type        = string
}

variable "services" {
  description = "(required)"
  type        = set(string)
}

variable "start_time" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_maintenance_window" "this" {
  description = var.description
  end_time    = var.end_time
  services    = var.services
  start_time  = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = pagerduty_maintenance_window.this.id
}

output "this" {
  value = pagerduty_maintenance_window.this
}
```

[top](#index)