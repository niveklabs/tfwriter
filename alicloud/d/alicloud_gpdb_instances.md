# alicloud_gpdb_instances

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
module "alicloud_gpdb_instances" {
  source = "./modules/alicloud/d/alicloud_gpdb_instances"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
data "alicloud_gpdb_instances" "this" {
  availability_zone = var.availability_zone
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  tags              = var.tags
  vswitch_id        = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_gpdb_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_gpdb_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_gpdb_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_gpdb_instances.this.names
}

output "this" {
  value = alicloud_gpdb_instances.this
}
```

[top](#index)