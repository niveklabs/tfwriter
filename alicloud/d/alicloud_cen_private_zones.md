# alicloud_cen_private_zones

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cen_private_zones" {
  source = "./modules/alicloud/d/alicloud_cen_private_zones"

  # cen_id - (required) is a type of string
  cen_id = null
  # host_region_id - (optional) is a type of string
  host_region_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "host_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
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
data "alicloud_cen_private_zones" "this" {
  cen_id         = var.cen_id
  host_region_id = var.host_region_id
  ids            = var.ids
  output_file    = var.output_file
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_private_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cen_private_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_cen_private_zones.this.zones
}

output "this" {
  value = alicloud_cen_private_zones.this
}
```

[top](#index)