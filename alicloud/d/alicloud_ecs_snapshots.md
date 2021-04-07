# alicloud_ecs_snapshots

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
module "alicloud_ecs_snapshots" {
  source = "./modules/alicloud/d/alicloud_ecs_snapshots"

  # category - (optional) is a type of string
  category = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # ids - (optional) is a type of list of string
  ids = []
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # snapshot_link_id - (optional) is a type of string
  snapshot_link_id = null
  # snapshot_name - (optional) is a type of string
  snapshot_name = null
  # snapshot_type - (optional) is a type of string
  snapshot_type = null
  # source_disk_type - (optional) is a type of string
  source_disk_type = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
  # usage - (optional) is a type of string
  usage = null
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

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
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

variable "snapshot_link_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_disk_type" {
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usage" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ecs_snapshots" "this" {
  # category - (optional) is a type of string
  category = var.category
  # dry_run - (optional) is a type of bool
  dry_run = var.dry_run
  # encrypted - (optional) is a type of bool
  encrypted = var.encrypted
  # ids - (optional) is a type of list of string
  ids = var.ids
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # snapshot_link_id - (optional) is a type of string
  snapshot_link_id = var.snapshot_link_id
  # snapshot_name - (optional) is a type of string
  snapshot_name = var.snapshot_name
  # snapshot_type - (optional) is a type of string
  snapshot_type = var.snapshot_type
  # source_disk_type - (optional) is a type of string
  source_disk_type = var.source_disk_type
  # status - (optional) is a type of string
  status = var.status
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type
  # usage - (optional) is a type of string
  usage = var.usage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ecs_snapshots.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_snapshots.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_snapshots.this.names
}

output "snapshots" {
  description = "returns a list of object"
  value       = data.alicloud_ecs_snapshots.this.snapshots
}

output "this" {
  value = alicloud_ecs_snapshots.this
}
```

[top](#index)