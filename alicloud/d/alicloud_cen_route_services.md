# alicloud_cen_route_services

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
module "alicloud_cen_route_services" {
  source = "./modules/alicloud/d/alicloud_cen_route_services"

  # access_region_id - (optional) is a type of string
  access_region_id = null
  # cen_id - (required) is a type of string
  cen_id = null
  # host - (optional) is a type of string
  host = null
  # host_region_id - (optional) is a type of string
  host_region_id = null
  # host_vpc_id - (optional) is a type of string
  host_vpc_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "access_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_vpc_id" {
  description = "(optional)"
  type        = string
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
data "alicloud_cen_route_services" "this" {
  access_region_id = var.access_region_id
  cen_id           = var.cen_id
  host             = var.host
  host_region_id   = var.host_region_id
  host_vpc_id      = var.host_vpc_id
  output_file      = var.output_file
  status           = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_route_services.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cen_route_services.this.ids
}

output "services" {
  description = "returns a list of object"
  value       = data.alicloud_cen_route_services.this.services
}

output "this" {
  value = alicloud_cen_route_services.this
}
```

[top](#index)