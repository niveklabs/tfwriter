# alicloud_slb_zones

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
module "alicloud_slb_zones" {
  source = "./modules/alicloud/d/alicloud_slb_zones"

  # available_slb_address_ip_version - (optional) is a type of string
  available_slb_address_ip_version = null
  # available_slb_address_type - (optional) is a type of string
  available_slb_address_type = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
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

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_slb_zones" "this" {
  # available_slb_address_ip_version - (optional) is a type of string
  available_slb_address_ip_version = var.available_slb_address_ip_version
  # available_slb_address_type - (optional) is a type of string
  available_slb_address_type = var.available_slb_address_type
  # enable_details - (optional) is a type of bool
  enable_details = var.enable_details
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_slb_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_slb_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_slb_zones.this.zones
}

output "this" {
  value = alicloud_slb_zones.this
}
```

[top](#index)