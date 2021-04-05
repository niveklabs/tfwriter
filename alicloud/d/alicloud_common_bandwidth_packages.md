# alicloud_common_bandwidth_packages

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_common_bandwidth_packages" {
  source = "./modules/alicloud/d/alicloud_common_bandwidth_packages"

  # bandwidth_package_name - (optional) is a type of string
  bandwidth_package_name = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # ids - (optional) is a type of list of string
  ids = []
  # include_reservation_data - (optional) is a type of bool
  include_reservation_data = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_package_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "include_reservation_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_common_bandwidth_packages" "this" {
  bandwidth_package_name   = var.bandwidth_package_name
  dry_run                  = var.dry_run
  ids                      = var.ids
  include_reservation_data = var.include_reservation_data
  name_regex               = var.name_regex
  output_file              = var.output_file
  resource_group_id        = var.resource_group_id
  status                   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_common_bandwidth_packages.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_common_bandwidth_packages.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_common_bandwidth_packages.this.names
}

output "packages" {
  description = "returns a list of object"
  value       = data.alicloud_common_bandwidth_packages.this.packages
}

output "this" {
  value = alicloud_common_bandwidth_packages.this
}
```

[top](#index)