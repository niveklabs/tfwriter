# alicloud_nas_mount_targets

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
module "alicloud_nas_mount_targets" {
  source = "./modules/alicloud/d/alicloud_nas_mount_targets"

  # access_group_name - (optional) is a type of string
  access_group_name = null
  # file_system_id - (required) is a type of string
  file_system_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # mount_target_domain - (optional) is a type of string
  mount_target_domain = null
  # network_type - (optional) is a type of string
  network_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_system_id" {
  description = "(required)"
  type        = string
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "mount_target_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_type" {
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

variable "type" {
  description = "(optional)"
  type        = string
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
data "alicloud_nas_mount_targets" "this" {
  access_group_name   = var.access_group_name
  file_system_id      = var.file_system_id
  ids                 = var.ids
  mount_target_domain = var.mount_target_domain
  network_type        = var.network_type
  output_file         = var.output_file
  status              = var.status
  type                = var.type
  vpc_id              = var.vpc_id
  vswitch_id          = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_nas_mount_targets.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_nas_mount_targets.this.ids
}

output "targets" {
  description = "returns a list of object"
  value       = data.alicloud_nas_mount_targets.this.targets
}

output "this" {
  value = alicloud_nas_mount_targets.this
}
```

[top](#index)