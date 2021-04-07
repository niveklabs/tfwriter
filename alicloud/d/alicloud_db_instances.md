# alicloud_db_instances

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
module "alicloud_db_instances" {
  source = "./modules/alicloud/d/alicloud_db_instances"

  # connection_mode - (optional) is a type of string
  connection_mode = null
  # db_type - (optional) is a type of string
  db_type = null
  # engine - (optional) is a type of string
  engine = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_db_instances" "this" {
  # connection_mode - (optional) is a type of string
  connection_mode = var.connection_mode
  # db_type - (optional) is a type of string
  db_type = var.db_type
  # engine - (optional) is a type of string
  engine = var.engine
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # status - (optional) is a type of string
  status = var.status
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_db_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_db_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_db_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_db_instances.this.names
}

output "this" {
  value = alicloud_db_instances.this
}
```

[top](#index)