# alicloud_market_order

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
module "alicloud_market_order" {
  source = "./modules/alicloud/r/alicloud_market_order"

  # components - (optional) is a type of map of string
  components = {}
  # coupon_id - (optional) is a type of string
  coupon_id = null
  # duration - (optional) is a type of number
  duration = null
  # package_version - (required) is a type of string
  package_version = null
  # pay_type - (optional) is a type of string
  pay_type = null
  # pricing_cycle - (required) is a type of string
  pricing_cycle = null
  # product_code - (required) is a type of string
  product_code = null
  # quantity - (optional) is a type of number
  quantity = null
}
```

[top](#index)

### Variables

```terraform
variable "components" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "coupon_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "package_version" {
  description = "(required)"
  type        = string
}

variable "pay_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pricing_cycle" {
  description = "(required)"
  type        = string
}

variable "product_code" {
  description = "(required)"
  type        = string
}

variable "quantity" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_market_order" "this" {
  components      = var.components
  coupon_id       = var.coupon_id
  duration        = var.duration
  package_version = var.package_version
  pay_type        = var.pay_type
  pricing_cycle   = var.pricing_cycle
  product_code    = var.product_code
  quantity        = var.quantity
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_market_order.this.id
}

output "this" {
  value = alicloud_market_order.this
}
```

[top](#index)