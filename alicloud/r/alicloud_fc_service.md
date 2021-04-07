# alicloud_fc_service

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
module "alicloud_fc_service" {
  source = "./modules/alicloud/r/alicloud_fc_service"

  # description - (optional) is a type of string
  description = null
  # internet_access - (optional) is a type of bool
  internet_access = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # publish - (optional) is a type of bool
  publish = null
  # role - (optional) is a type of string
  role = null

  log_config = [{
    logstore = null
    project  = null
  }]

  nas_config = [{
    group_id = null
    mount_points = [{
      mount_dir   = null
      server_addr = null
    }]
    user_id = null
  }]

  vpc_config = [{
    security_group_id = null
    vpc_id            = null
    vswitch_ids       = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publish" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      logstore = string
      project  = string
    }
  ))
  default = []
}

variable "nas_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group_id = number
      mount_points = list(object(
        {
          mount_dir   = string
          server_addr = string
        }
      ))
      user_id = number
    }
  ))
  default = []
}

variable "vpc_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group_id = string
      vpc_id            = string
      vswitch_ids       = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_fc_service" "this" {
  # description - (optional) is a type of string
  description = var.description
  # internet_access - (optional) is a type of bool
  internet_access = var.internet_access
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # publish - (optional) is a type of bool
  publish = var.publish
  # role - (optional) is a type of string
  role = var.role

  dynamic "log_config" {
    for_each = var.log_config
    content {
      # logstore - (required) is a type of string
      logstore = log_config.value["logstore"]
      # project - (required) is a type of string
      project = log_config.value["project"]
    }
  }

  dynamic "nas_config" {
    for_each = var.nas_config
    content {
      # group_id - (required) is a type of number
      group_id = nas_config.value["group_id"]
      # user_id - (required) is a type of number
      user_id = nas_config.value["user_id"]

      dynamic "mount_points" {
        for_each = nas_config.value.mount_points
        content {
          # mount_dir - (required) is a type of string
          mount_dir = mount_points.value["mount_dir"]
          # server_addr - (required) is a type of string
          server_addr = mount_points.value["server_addr"]
        }
      }

    }
  }

  dynamic "vpc_config" {
    for_each = var.vpc_config
    content {
      # security_group_id - (required) is a type of string
      security_group_id = vpc_config.value["security_group_id"]
      # vswitch_ids - (required) is a type of set of string
      vswitch_ids = vpc_config.value["vswitch_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_fc_service.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = alicloud_fc_service.this.last_modified
}

output "name" {
  description = "returns a string"
  value       = alicloud_fc_service.this.name
}

output "service_id" {
  description = "returns a string"
  value       = alicloud_fc_service.this.service_id
}

output "version" {
  description = "returns a string"
  value       = alicloud_fc_service.this.version
}

output "this" {
  value = alicloud_fc_service.this
}
```

[top](#index)