# alicloud_vswitches

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
module "alicloud_vswitches" {
  source = "./modules/alicloud/d/alicloud_vswitches"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # ids - (optional) is a type of list of string
  ids = []
  # is_default - (optional) is a type of bool
  is_default = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_name - (optional) is a type of string
  vswitch_name = null
  # vswitch_owner_id - (optional) is a type of number
  vswitch_owner_id = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "is_default" {
  description = "(optional)"
  type        = bool
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

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
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

variable "vswitch_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_owner_id" {
  description = "(optional)"
  type        = number
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
data "alicloud_vswitches" "this" {
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # dry_run - (optional) is a type of bool
  dry_run = var.dry_run
  # ids - (optional) is a type of list of string
  ids = var.ids
  # is_default - (optional) is a type of bool
  is_default = var.is_default
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # route_table_id - (optional) is a type of string
  route_table_id = var.route_table_id
  # status - (optional) is a type of string
  status = var.status
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
  # vswitch_name - (optional) is a type of string
  vswitch_name = var.vswitch_name
  # vswitch_owner_id - (optional) is a type of number
  vswitch_owner_id = var.vswitch_owner_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_vswitches.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_vswitches.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_vswitches.this.names
}

output "vswitches" {
  description = "returns a list of object"
  value       = data.alicloud_vswitches.this.vswitches
}

output "this" {
  value = alicloud_vswitches.this
}
```

[top](#index)