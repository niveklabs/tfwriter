# thunder_reboot

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_reboot" {
  source = "./modules/thunder/r/thunder_reboot"

  # all - (optional) is a type of number
  all = null
  # at - (optional) is a type of number
  at = null
  # cancel - (optional) is a type of number
  cancel = null
  # day_of_month - (optional) is a type of number
  day_of_month = null
  # day_of_month_2 - (optional) is a type of number
  day_of_month_2 = null
  # device - (optional) is a type of number
  device = null
  # in - (optional) is a type of string
  in = null
  # month - (optional) is a type of string
  month = null
  # month_2 - (optional) is a type of string
  month_2 = null
  # reason - (optional) is a type of string
  reason = null
  # reason_2 - (optional) is a type of string
  reason_2 = null
  # reason_3 - (optional) is a type of string
  reason_3 = null
  # time - (optional) is a type of string
  time = null
}
```

[top](#index)

### Variables

```terraform
variable "all" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "at" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cancel" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "day_of_month" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "day_of_month_2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "month" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "month_2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reason" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reason_2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reason_3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_reboot" "this" {
  all            = var.all
  at             = var.at
  cancel         = var.cancel
  day_of_month   = var.day_of_month
  day_of_month_2 = var.day_of_month_2
  device         = var.device
  in             = var.in
  month          = var.month
  month_2        = var.month_2
  reason         = var.reason
  reason_2       = var.reason_2
  reason_3       = var.reason_3
  time           = var.time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_reboot.this.id
}

output "this" {
  value = thunder_reboot.this
}
```

[top](#index)