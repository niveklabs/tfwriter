# alicloud_ga_bandwidth_package

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
module "alicloud_ga_bandwidth_package" {
  source = "./modules/alicloud/r/alicloud_ga_bandwidth_package"

  # auto_pay - (optional) is a type of bool
  auto_pay = null
  # auto_use_coupon - (optional) is a type of bool
  auto_use_coupon = null
  # bandwidth - (required) is a type of number
  bandwidth = null
  # bandwidth_package_name - (optional) is a type of string
  bandwidth_package_name = null
  # bandwidth_type - (optional) is a type of string
  bandwidth_type = null
  # billing_type - (optional) is a type of string
  billing_type = null
  # cbn_geographic_region_ida - (optional) is a type of string
  cbn_geographic_region_ida = null
  # cbn_geographic_region_idb - (optional) is a type of string
  cbn_geographic_region_idb = null
  # description - (optional) is a type of string
  description = null
  # duration - (optional) is a type of string
  duration = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # ratio - (optional) is a type of number
  ratio = null
  # type - (required) is a type of string
  type = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_pay" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_use_coupon" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bandwidth" {
  description = "(required)"
  type        = number
}

variable "bandwidth_package_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bandwidth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "billing_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cbn_geographic_region_ida" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cbn_geographic_region_idb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ratio" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
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
resource "alicloud_ga_bandwidth_package" "this" {
  auto_pay                  = var.auto_pay
  auto_use_coupon           = var.auto_use_coupon
  bandwidth                 = var.bandwidth
  bandwidth_package_name    = var.bandwidth_package_name
  bandwidth_type            = var.bandwidth_type
  billing_type              = var.billing_type
  cbn_geographic_region_ida = var.cbn_geographic_region_ida
  cbn_geographic_region_idb = var.cbn_geographic_region_idb
  description               = var.description
  duration                  = var.duration
  payment_type              = var.payment_type
  ratio                     = var.ratio
  type                      = var.type

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
  value       = alicloud_ga_bandwidth_package.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ga_bandwidth_package.this.status
}

output "this" {
  value = alicloud_ga_bandwidth_package.this
}
```

[top](#index)