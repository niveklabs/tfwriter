# alicloud_ons_groups

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
module "alicloud_ons_groups" {
  source = "./modules/alicloud/d/alicloud_ons_groups"

  # group_id_regex - (optional) is a type of string
  group_id_regex = null
  # group_type - (optional) is a type of string
  group_type = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "group_id_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_ons_groups" "this" {
  group_id_regex = var.group_id_regex
  group_type     = var.group_type
  ids            = var.ids
  instance_id    = var.instance_id
  name_regex     = var.name_regex
  output_file    = var.output_file
  tags           = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.alicloud_ons_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ons_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ons_groups.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ons_groups.this.names
}

output "this" {
  value = alicloud_ons_groups.this
}
```

[top](#index)