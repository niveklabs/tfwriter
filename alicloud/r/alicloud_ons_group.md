# alicloud_ons_group

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
module "alicloud_ons_group" {
  source = "./modules/alicloud/r/alicloud_ons_group"

  # group_id - (optional) is a type of string
  group_id = null
  # group_name - (optional) is a type of string
  group_name = null
  # group_type - (optional) is a type of string
  group_type = null
  # instance_id - (required) is a type of string
  instance_id = null
  # read_enable - (optional) is a type of bool
  read_enable = null
  # remark - (optional) is a type of string
  remark = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "read_enable" {
  description = "(optional)"
  type        = bool
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
resource "alicloud_ons_group" "this" {
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # group_name - (optional) is a type of string
  group_name = var.group_name
  # group_type - (optional) is a type of string
  group_type = var.group_type
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # read_enable - (optional) is a type of bool
  read_enable = var.read_enable
  # remark - (optional) is a type of string
  remark = var.remark
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "group_id" {
  description = "returns a string"
  value       = alicloud_ons_group.this.group_id
}

output "group_name" {
  description = "returns a string"
  value       = alicloud_ons_group.this.group_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_ons_group.this.id
}

output "this" {
  value = alicloud_ons_group.this
}
```

[top](#index)