# alicloud_hbase_instance_types

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
module "alicloud_hbase_instance_types" {
  source = "./modules/alicloud/d/alicloud_hbase_instance_types"

  # charge_type - (optional) is a type of string
  charge_type = null
  # disk_type - (optional) is a type of string
  disk_type = null
  # engine - (optional) is a type of string
  engine = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # region_id - (optional) is a type of string
  region_id = null
  # version - (optional) is a type of string
  version = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_hbase_instance_types" "this" {
  charge_type   = var.charge_type
  disk_type     = var.disk_type
  engine        = var.engine
  instance_type = var.instance_type
  output_file   = var.output_file
  region_id     = var.region_id
  version       = var.version
  zone_id       = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "core_instance_types" {
  description = "returns a list of object"
  value       = data.alicloud_hbase_instance_types.this.core_instance_types
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_hbase_instance_types.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_hbase_instance_types.this.ids
}

output "master_instance_types" {
  description = "returns a list of object"
  value       = data.alicloud_hbase_instance_types.this.master_instance_types
}

output "types" {
  description = "returns a list of object"
  value       = data.alicloud_hbase_instance_types.this.types
}

output "this" {
  value = alicloud_hbase_instance_types.this
}
```

[top](#index)