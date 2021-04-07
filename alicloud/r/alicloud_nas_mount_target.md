# alicloud_nas_mount_target

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
module "alicloud_nas_mount_target" {
  source = "./modules/alicloud/r/alicloud_nas_mount_target"

  # access_group_name - (optional) is a type of string
  access_group_name = null
  # file_system_id - (required) is a type of string
  file_system_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # status - (optional) is a type of string
  status = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null

  timeouts = [{
    create = null
  }]
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

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_nas_mount_target" "this" {
  # access_group_name - (optional) is a type of string
  access_group_name = var.access_group_name
  # file_system_id - (required) is a type of string
  file_system_id = var.file_system_id
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # status - (optional) is a type of string
  status = var.status
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
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
  value       = alicloud_nas_mount_target.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_nas_mount_target.this.status
}

output "this" {
  value = alicloud_nas_mount_target.this
}
```

[top](#index)