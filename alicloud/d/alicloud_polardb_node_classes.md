# alicloud_polardb_node_classes

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
module "alicloud_polardb_node_classes" {
  source = "./modules/alicloud/d/alicloud_polardb_node_classes"

  # db_node_class - (optional) is a type of string
  db_node_class = null
  # db_type - (optional) is a type of string
  db_type = null
  # db_version - (optional) is a type of string
  db_version = null
  # output_file - (optional) is a type of string
  output_file = null
  # pay_type - (required) is a type of string
  pay_type = null
  # region_id - (optional) is a type of string
  region_id = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_node_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pay_type" {
  description = "(required)"
  type        = string
}

variable "region_id" {
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
data "alicloud_polardb_node_classes" "this" {
  db_node_class = var.db_node_class
  db_type       = var.db_type
  db_version    = var.db_version
  output_file   = var.output_file
  pay_type      = var.pay_type
  region_id     = var.region_id
  zone_id       = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "classes" {
  description = "returns a list of object"
  value       = data.alicloud_polardb_node_classes.this.classes
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_polardb_node_classes.this.id
}

output "this" {
  value = alicloud_polardb_node_classes.this
}
```

[top](#index)