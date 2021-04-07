# alicloud_images

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
module "alicloud_images" {
  source = "./modules/alicloud/d/alicloud_images"

  # action_type - (optional) is a type of string
  action_type = null
  # architecture - (optional) is a type of string
  architecture = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # image_family - (optional) is a type of string
  image_family = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # is_support_cloud_init - (optional) is a type of bool
  is_support_cloud_init = null
  # is_support_io_optimized - (optional) is a type of bool
  is_support_io_optimized = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # os_type - (optional) is a type of string
  os_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # owners - (optional) is a type of string
  owners = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # usage - (optional) is a type of string
  usage = null
}
```

[top](#index)

### Variables

```terraform
variable "action_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "architecture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "image_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_support_cloud_init" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_support_io_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owners" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_id" {
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

variable "usage" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_images" "this" {
  # action_type - (optional) is a type of string
  action_type = var.action_type
  # architecture - (optional) is a type of string
  architecture = var.architecture
  # dry_run - (optional) is a type of bool
  dry_run = var.dry_run
  # image_family - (optional) is a type of string
  image_family = var.image_family
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # is_support_cloud_init - (optional) is a type of bool
  is_support_cloud_init = var.is_support_cloud_init
  # is_support_io_optimized - (optional) is a type of bool
  is_support_io_optimized = var.is_support_io_optimized
  # most_recent - (optional) is a type of bool
  most_recent = var.most_recent
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # os_type - (optional) is a type of string
  os_type = var.os_type
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # owners - (optional) is a type of string
  owners = var.owners
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # status - (optional) is a type of string
  status = var.status
  # tags - (optional) is a type of map of string
  tags = var.tags
  # usage - (optional) is a type of string
  usage = var.usage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_images.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_images.this.ids
}

output "images" {
  description = "returns a list of object"
  value       = data.alicloud_images.this.images
}

output "this" {
  value = alicloud_images.this
}
```

[top](#index)