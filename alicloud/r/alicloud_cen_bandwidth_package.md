# alicloud_cen_bandwidth_package

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
module "alicloud_cen_bandwidth_package" {
  source = "./modules/alicloud/r/alicloud_cen_bandwidth_package"

  # bandwidth - (required) is a type of number
  bandwidth = null
  # cen_bandwidth_package_name - (optional) is a type of string
  cen_bandwidth_package_name = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # description - (optional) is a type of string
  description = null
  # geographic_region_a_id - (optional) is a type of string
  geographic_region_a_id = null
  # geographic_region_b_id - (optional) is a type of string
  geographic_region_b_id = null
  # geographic_region_ids - (optional) is a type of set of string
  geographic_region_ids = []
  # name - (optional) is a type of string
  name = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # period - (optional) is a type of number
  period = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = number
}

variable "cen_bandwidth_package_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geographic_region_a_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geographic_region_b_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geographic_region_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_bandwidth_package" "this" {
  bandwidth                  = var.bandwidth
  cen_bandwidth_package_name = var.cen_bandwidth_package_name
  charge_type                = var.charge_type
  description                = var.description
  geographic_region_a_id     = var.geographic_region_a_id
  geographic_region_b_id     = var.geographic_region_b_id
  geographic_region_ids      = var.geographic_region_ids
  name                       = var.name
  payment_type               = var.payment_type
  period                     = var.period

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cen_bandwidth_package_name" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.cen_bandwidth_package_name
}

output "charge_type" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.charge_type
}

output "expired_time" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.expired_time
}

output "geographic_region_a_id" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.geographic_region_a_id
}

output "geographic_region_b_id" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.geographic_region_b_id
}

output "geographic_region_ids" {
  description = "returns a set of string"
  value       = alicloud_cen_bandwidth_package.this.geographic_region_ids
}

output "id" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.name
}

output "payment_type" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.payment_type
}

output "status" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package.this.status
}

output "this" {
  value = alicloud_cen_bandwidth_package.this
}
```

[top](#index)