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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_common_bandwidth_package" {
  source = "./modules/alicloud/r/alicloud_common_bandwidth_package"

  # bandwidth - (required) is a type of string
  bandwidth = null
  # bandwidth_package_name - (optional) is a type of string
  bandwidth_package_name = null
  # description - (optional) is a type of string
  description = null
  # force - (optional) is a type of string
  force = null
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
  # zone - (optional) is a type of string
  zone = null

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
  type        = string
}

variable "bandwidth_package_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force" {
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

variable "zone" {
  description = "(optional)"
  type        = string
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
resource "alicloud_common_bandwidth_package" "this" {
  bandwidth              = var.bandwidth
  bandwidth_package_name = var.bandwidth_package_name
  description            = var.description
  force                  = var.force
  internet_charge_type   = var.internet_charge_type
  isp                    = var.isp
  name                   = var.name
  ratio                  = var.ratio
  resource_group_id      = var.resource_group_id
  zone                   = var.zone

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
output "bandwidth_package_name" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.bandwidth_package_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.name
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.resource_group_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_common_bandwidth_package.this.status
}

output "this" {
  value = alicloud_common_bandwidth_package.this
}
```

[top](#index)