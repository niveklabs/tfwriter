# alicloud_kvstore_instance_classes

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
module "alicloud_kvstore_instance_classes" {
  source = "./modules/alicloud/d/alicloud_kvstore_instance_classes"

  # architecture - (optional) is a type of string
  architecture = null
  # edition_type - (optional) is a type of string
  edition_type = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # node_type - (optional) is a type of string
  node_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # package_type - (optional) is a type of string
  package_type = null
  # performance_type - (optional) is a type of string
  performance_type = null
  # series_type - (optional) is a type of string
  series_type = null
  # shard_number - (optional) is a type of number
  shard_number = null
  # sorted_by - (optional) is a type of string
  sorted_by = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "architecture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edition_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "performance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "series_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shard_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sorted_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_kvstore_instance_classes" "this" {
  architecture         = var.architecture
  edition_type         = var.edition_type
  engine               = var.engine
  engine_version       = var.engine_version
  instance_charge_type = var.instance_charge_type
  node_type            = var.node_type
  output_file          = var.output_file
  package_type         = var.package_type
  performance_type     = var.performance_type
  series_type          = var.series_type
  shard_number         = var.shard_number
  sorted_by            = var.sorted_by
  storage_type         = var.storage_type
  zone_id              = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "classes" {
  description = "returns a list of object"
  value       = data.alicloud_kvstore_instance_classes.this.classes
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_kvstore_instance_classes.this.id
}

output "instance_classes" {
  description = "returns a list of string"
  value       = data.alicloud_kvstore_instance_classes.this.instance_classes
}

output "this" {
  value = alicloud_kvstore_instance_classes.this
}
```

[top](#index)