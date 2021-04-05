# alicloud_sag_qos_car

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_sag_qos_car" {
  source = "./modules/alicloud/r/alicloud_sag_qos_car"

  # description - (optional) is a type of string
  description = null
  # limit_type - (required) is a type of string
  limit_type = null
  # max_bandwidth_abs - (optional) is a type of number
  max_bandwidth_abs = null
  # max_bandwidth_percent - (optional) is a type of number
  max_bandwidth_percent = null
  # min_bandwidth_abs - (optional) is a type of number
  min_bandwidth_abs = null
  # min_bandwidth_percent - (optional) is a type of number
  min_bandwidth_percent = null
  # name - (optional) is a type of string
  name = null
  # percent_source_type - (optional) is a type of string
  percent_source_type = null
  # priority - (required) is a type of number
  priority = null
  # qos_id - (required) is a type of string
  qos_id = null
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

variable "limit_type" {
  description = "(required)"
  type        = string
}

variable "max_bandwidth_abs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_bandwidth_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_bandwidth_abs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_bandwidth_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "percent_source_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "qos_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_sag_qos_car" "this" {
  description           = var.description
  limit_type            = var.limit_type
  max_bandwidth_abs     = var.max_bandwidth_abs
  max_bandwidth_percent = var.max_bandwidth_percent
  min_bandwidth_abs     = var.min_bandwidth_abs
  min_bandwidth_percent = var.min_bandwidth_percent
  name                  = var.name
  percent_source_type   = var.percent_source_type
  priority              = var.priority
  qos_id                = var.qos_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_sag_qos_car.this.id
}

output "this" {
  value = alicloud_sag_qos_car.this
}
```

[top](#index)