# alicloud_db_instance_classes

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
module "alicloud_db_instance_classes" {
  source = "./modules/alicloud/d/alicloud_db_instance_classes"

  # category - (optional) is a type of string
  category = null
  # db_instance_class - (optional) is a type of string
  db_instance_class = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # multi_zone - (optional) is a type of bool
  multi_zone = null
  # output_file - (optional) is a type of string
  output_file = null
  # sorted_by - (optional) is a type of string
  sorted_by = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_instance_class" {
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

variable "multi_zone" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
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
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_db_instance_classes" "this" {
  # category - (optional) is a type of string
  category = var.category
  # db_instance_class - (optional) is a type of string
  db_instance_class = var.db_instance_class
  # engine - (optional) is a type of string
  engine = var.engine
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # multi_zone - (optional) is a type of bool
  multi_zone = var.multi_zone
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # sorted_by - (optional) is a type of string
  sorted_by = var.sorted_by
  # storage_type - (optional) is a type of string
  storage_type = var.storage_type
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_db_instance_classes.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_db_instance_classes.this.ids
}

output "instance_classes" {
  description = "returns a list of object"
  value       = data.alicloud_db_instance_classes.this.instance_classes
}

output "this" {
  value = alicloud_db_instance_classes.this
}
```

[top](#index)