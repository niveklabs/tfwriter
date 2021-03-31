# alicloud_common_bandwidth_package

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
module "alicloud_common_bandwidth_package" {
  source = "./modules/alicloud/r/alicloud_common_bandwidth_package"

  # bandwidth - (required) is a type of number
  bandwidth = null
  # description - (optional) is a type of string
  description = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # isp - (optional) is a type of string
  isp = null
  # name - (optional) is a type of string
  name = null
  # ratio - (optional) is a type of number
  ratio = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ratio" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_common_bandwidth_package" "this" {
  bandwidth            = var.bandwidth
  description          = var.description
  internet_charge_type = var.internet_charge_type
  isp                  = var.isp
  name                 = var.name
  ratio                = var.ratio
  resource_group_id    = var.resource_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.resource_group_id
}

output "this" {
  value = alicloud_common_bandwidth_package.this
}
```

[top](#index)