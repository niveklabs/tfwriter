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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_common_bandwidth_packages" {
  source = "./modules/alicloud/d/alicloud_common_bandwidth_packages"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_common_bandwidth_packages" "this" {
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
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