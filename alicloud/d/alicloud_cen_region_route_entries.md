# alicloud_cen_region_route_entries

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
module "alicloud_cen_region_route_entries" {
  source = "./modules/alicloud/d/alicloud_cen_region_route_entries"

  # instance_id - (required) is a type of string
  instance_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # region_id - (required) is a type of string
  region_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cen_region_route_entries" "this" {
  instance_id = var.instance_id
  output_file = var.output_file
  region_id   = var.region_id
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.alicloud_cen_region_route_entries.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_region_route_entries.this.id
}

output "this" {
  value = alicloud_cen_region_route_entries.this
}
```

[top](#index)