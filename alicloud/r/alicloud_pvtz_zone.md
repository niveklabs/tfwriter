# alicloud_pvtz_zone

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_pvtz_zone" {
  source = "./modules/alicloud/r/alicloud_pvtz_zone"

  # lang - (optional) is a type of string
  lang = null
  # name - (optional) is a type of string
  name = null
  # proxy_pattern - (optional) is a type of string
  proxy_pattern = null
  # remark - (optional) is a type of string
  remark = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
  # zone_name - (optional) is a type of string
  zone_name = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_name" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_pvtz_zone" "this" {
  lang              = var.lang
  name              = var.name
  proxy_pattern     = var.proxy_pattern
  remark            = var.remark
  resource_group_id = var.resource_group_id
  user_client_ip    = var.user_client_ip
  zone_name         = var.zone_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_time" {
  description = "returns a string"
  value       = alicloud_pvtz_zone.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_pvtz_zone.this.id
}

output "is_ptr" {
  description = "returns a bool"
  value       = alicloud_pvtz_zone.this.is_ptr
}

output "name" {
  description = "returns a string"
  value       = alicloud_pvtz_zone.this.name
}

output "record_count" {
  description = "returns a number"
  value       = alicloud_pvtz_zone.this.record_count
}

output "update_time" {
  description = "returns a string"
  value       = alicloud_pvtz_zone.this.update_time
}

output "zone_name" {
  description = "returns a string"
  value       = alicloud_pvtz_zone.this.zone_name
}

output "this" {
  value = alicloud_pvtz_zone.this
}
```

[top](#index)