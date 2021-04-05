# alicloud_alikafka_topic

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
module "alicloud_alikafka_topic" {
  source = "./modules/alicloud/r/alicloud_alikafka_topic"

  # compact_topic - (optional) is a type of bool
  compact_topic = null
  # instance_id - (required) is a type of string
  instance_id = null
  # local_topic - (optional) is a type of bool
  local_topic = null
  # partition_num - (optional) is a type of number
  partition_num = null
  # remark - (required) is a type of string
  remark = null
  # tags - (optional) is a type of map of string
  tags = {}
  # topic - (required) is a type of string
  topic = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compact_topic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "local_topic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "partition_num" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remark" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "topic" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alikafka_topic" "this" {
  compact_topic = var.compact_topic
  instance_id   = var.instance_id
  local_topic   = var.local_topic
  partition_num = var.partition_num
  remark        = var.remark
  tags          = var.tags
  topic         = var.topic

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_alikafka_topic.this.id
}

output "this" {
  value = alicloud_alikafka_topic.this
}
```

[top](#index)