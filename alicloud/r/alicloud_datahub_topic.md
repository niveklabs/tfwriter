# alicloud_datahub_topic

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_datahub_topic" {
  source = "./modules/alicloud/r/alicloud_datahub_topic"

  # comment - (optional) is a type of string
  comment = null
  # life_cycle - (optional) is a type of number
  life_cycle = null
  # name - (required) is a type of string
  name = null
  # project_name - (required) is a type of string
  project_name = null
  # record_schema - (optional) is a type of map of string
  record_schema = {}
  # record_type - (optional) is a type of string
  record_type = null
  # shard_count - (optional) is a type of number
  shard_count = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "life_cycle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_name" {
  description = "(required)"
  type        = string
}

variable "record_schema" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "record_type" {
  description = "(optional)"
  type        = string
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
resource "alicloud_datahub_topic" "this" {
  comment       = var.comment
  life_cycle    = var.life_cycle
  name          = var.name
  project_name  = var.project_name
  record_schema = var.record_schema
  record_type   = var.record_type
  shard_count   = var.shard_count
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = alicloud_datahub_topic.this.create_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_datahub_topic.this.id
}

output "last_modify_time" {
  description = "returns a string"
  value       = alicloud_datahub_topic.this.last_modify_time
}

output "this" {
  value = alicloud_datahub_topic.this
}
```

[top](#index)