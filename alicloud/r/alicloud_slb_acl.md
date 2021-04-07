# alicloud_slb_acl

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
module "alicloud_slb_acl" {
  source = "./modules/alicloud/r/alicloud_slb_acl"

  # ip_version - (optional) is a type of string
  ip_version = null
  # name - (required) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  entry_list = [{
    comment = null
    entry   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "entry_list" {
  description = "nested block: NestingSet, min items: 0, max items: 300"
  type = set(object(
    {
      comment = string
      entry   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_acl" "this" {
  # ip_version - (optional) is a type of string
  ip_version = var.ip_version
  # name - (required) is a type of string
  name = var.name
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "entry_list" {
    for_each = var.entry_list
    content {
      # comment - (optional) is a type of string
      comment = entry_list.value["comment"]
      # entry - (required) is a type of string
      entry = entry_list.value["entry"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_slb_acl.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_slb_acl.this.resource_group_id
}

output "this" {
  value = alicloud_slb_acl.this
}
```

[top](#index)