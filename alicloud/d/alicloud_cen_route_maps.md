# alicloud_cen_route_maps

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
module "alicloud_cen_route_maps" {
  source = "./modules/alicloud/d/alicloud_cen_route_maps"

  # cen_id - (required) is a type of string
  cen_id = null
  # cen_region_id - (optional) is a type of string
  cen_region_id = null
  # description_regex - (optional) is a type of string
  description_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
  # transmit_direction - (optional) is a type of string
  transmit_direction = null
}
```

[top](#index)

### Variables

```terraform
variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "cen_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description_regex" {
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

variable "transmit_direction" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cen_route_maps" "this" {
  cen_id             = var.cen_id
  cen_region_id      = var.cen_region_id
  description_regex  = var.description_regex
  ids                = var.ids
  output_file        = var.output_file
  status             = var.status
  transmit_direction = var.transmit_direction
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_route_maps.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cen_route_maps.this.ids
}

output "maps" {
  description = "returns a list of object"
  value       = data.alicloud_cen_route_maps.this.maps
}

output "this" {
  value = alicloud_cen_route_maps.this
}
```

[top](#index)