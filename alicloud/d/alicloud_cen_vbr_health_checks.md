# alicloud_cen_vbr_health_checks

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
module "alicloud_cen_vbr_health_checks" {
  source = "./modules/alicloud/d/alicloud_cen_vbr_health_checks"

  # cen_id - (optional) is a type of string
  cen_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # vbr_instance_id - (optional) is a type of string
  vbr_instance_id = null
  # vbr_instance_owner_id - (optional) is a type of number
  vbr_instance_owner_id = null
  # vbr_instance_region_id - (required) is a type of string
  vbr_instance_region_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cen_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vbr_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vbr_instance_owner_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vbr_instance_region_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cen_vbr_health_checks" "this" {
  cen_id                 = var.cen_id
  output_file            = var.output_file
  vbr_instance_id        = var.vbr_instance_id
  vbr_instance_owner_id  = var.vbr_instance_owner_id
  vbr_instance_region_id = var.vbr_instance_region_id
}
```

[top](#index)

### Outputs

```terraform
output "checks" {
  description = "returns a list of object"
  value       = data.alicloud_cen_vbr_health_checks.this.checks
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_vbr_health_checks.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cen_vbr_health_checks.this.ids
}

output "this" {
  value = alicloud_cen_vbr_health_checks.this
}
```

[top](#index)