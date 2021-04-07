# alicloud_log_store

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "alicloud_log_store" {
  source = "./modules/alicloud/r/alicloud_log_store"

  # append_meta - (optional) is a type of bool
  append_meta = null
  # auto_split - (optional) is a type of bool
  auto_split = null
  # enable_web_tracking - (optional) is a type of bool
  enable_web_tracking = null
  # max_split_shard_count - (optional) is a type of number
  max_split_shard_count = null
  # name - (required) is a type of string
  name = null
  # project - (required) is a type of string
  project = null
  # retention_period - (optional) is a type of number
  retention_period = null
  # shard_count - (optional) is a type of number
  shard_count = null
}
```

[top](#index)

### Variables

```terraform
variable "append_meta" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_split" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_web_tracking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_split_shard_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shard_count" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_log_store" "this" {
  # append_meta - (optional) is a type of bool
  append_meta = var.append_meta
  # auto_split - (optional) is a type of bool
  auto_split = var.auto_split
  # enable_web_tracking - (optional) is a type of bool
  enable_web_tracking = var.enable_web_tracking
  # max_split_shard_count - (optional) is a type of number
  max_split_shard_count = var.max_split_shard_count
  # name - (required) is a type of string
  name = var.name
  # project - (required) is a type of string
  project = var.project
  # retention_period - (optional) is a type of number
  retention_period = var.retention_period
  # shard_count - (optional) is a type of number
  shard_count = var.shard_count
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_log_store.this.id
}

output "shards" {
  description = "returns a list of object"
  value       = alicloud_log_store.this.shards
}

output "this" {
  value = alicloud_log_store.this
}
```

[top](#index)