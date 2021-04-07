# alicloud_ons_topic

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
module "alicloud_ons_topic" {
  source = "./modules/alicloud/r/alicloud_ons_topic"

  # instance_id - (required) is a type of string
  instance_id = null
  # message_type - (required) is a type of number
  message_type = null
  # perm - (optional) is a type of number
  perm = null
  # remark - (optional) is a type of string
  remark = null
  # tags - (optional) is a type of map of string
  tags = {}
  # topic - (optional) is a type of string
  topic = null
  # topic_name - (optional) is a type of string
  topic_name = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "message_type" {
  description = "(required)"
  type        = number
}

variable "perm" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "topic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topic_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ons_topic" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # message_type - (required) is a type of number
  message_type = var.message_type
  # perm - (optional) is a type of number
  perm = var.perm
  # remark - (optional) is a type of string
  remark = var.remark
  # tags - (optional) is a type of map of string
  tags = var.tags
  # topic - (optional) is a type of string
  topic = var.topic
  # topic_name - (optional) is a type of string
  topic_name = var.topic_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ons_topic.this.id
}

output "topic" {
  description = "returns a string"
  value       = alicloud_ons_topic.this.topic
}

output "topic_name" {
  description = "returns a string"
  value       = alicloud_ons_topic.this.topic_name
}

output "this" {
  value = alicloud_ons_topic.this
}
```

[top](#index)