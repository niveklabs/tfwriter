# alicloud_ga_accelerator

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ga_accelerator" {
  source = "./modules/alicloud/r/alicloud_ga_accelerator"

  # accelerator_name - (optional) is a type of string
  accelerator_name = null
  # auto_use_coupon - (optional) is a type of bool
  auto_use_coupon = null
  # description - (optional) is a type of string
  description = null
  # duration - (required) is a type of number
  duration = null
  # spec - (required) is a type of string
  spec = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accelerator_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_use_coupon" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration" {
  description = "(required)"
  type        = number
}

variable "spec" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ga_accelerator" "this" {
  accelerator_name = var.accelerator_name
  auto_use_coupon  = var.auto_use_coupon
  description      = var.description
  duration         = var.duration
  spec             = var.spec

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ga_accelerator.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ga_accelerator.this.status
}

output "this" {
  value = alicloud_ga_accelerator.this
}
```

[top](#index)