# alicloud_zones

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
module "alicloud_zones" {
  source = "./modules/alicloud/d/alicloud_zones"

  # available_disk_category - (optional) is a type of string
  available_disk_category = null
  # available_instance_type - (optional) is a type of string
  available_instance_type = null
  # available_resource_creation - (optional) is a type of string
  available_resource_creation = null
  # available_slb_address_ip_version - (optional) is a type of string
  available_slb_address_ip_version = null
  # available_slb_address_type - (optional) is a type of string
  available_slb_address_type = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # multi - (optional) is a type of bool
  multi = null
  # network_type - (optional) is a type of string
  network_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # spot_strategy - (optional) is a type of string
  spot_strategy = null
}
```

[top](#index)

### Variables

```terraform
variable "available_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "available_instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "available_resource_creation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "available_slb_address_ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "available_slb_address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_zones" "this" {
  # available_disk_category - (optional) is a type of string
  available_disk_category = var.available_disk_category
  # available_instance_type - (optional) is a type of string
  available_instance_type = var.available_instance_type
  # available_resource_creation - (optional) is a type of string
  available_resource_creation = var.available_resource_creation
  # available_slb_address_ip_version - (optional) is a type of string
  available_slb_address_ip_version = var.available_slb_address_ip_version
  # available_slb_address_type - (optional) is a type of string
  available_slb_address_type = var.available_slb_address_type
  # enable_details - (optional) is a type of bool
  enable_details = var.enable_details
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # multi - (optional) is a type of bool
  multi = var.multi
  # network_type - (optional) is a type of string
  network_type = var.network_type
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # spot_strategy - (optional) is a type of string
  spot_strategy = var.spot_strategy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_zones.this.zones
}

output "this" {
  value = alicloud_zones.this
}
```

[top](#index)