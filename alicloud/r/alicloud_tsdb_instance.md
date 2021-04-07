# alicloud_tsdb_instance

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
module "alicloud_tsdb_instance" {
  source = "./modules/alicloud/r/alicloud_tsdb_instance"

  # app_key - (optional) is a type of string
  app_key = null
  # disk_category - (optional) is a type of string
  disk_category = null
  # duration - (optional) is a type of string
  duration = null
  # engine_type - (optional) is a type of string
  engine_type = null
  # instance_alias - (optional) is a type of string
  instance_alias = null
  # instance_class - (required) is a type of string
  instance_class = null
  # instance_storage - (required) is a type of string
  instance_storage = null
  # payment_type - (required) is a type of string
  payment_type = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_class" {
  description = "(required)"
  type        = string
}

variable "instance_storage" {
  description = "(required)"
  type        = string
}

variable "payment_type" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_tsdb_instance" "this" {
  # app_key - (optional) is a type of string
  app_key = var.app_key
  # disk_category - (optional) is a type of string
  disk_category = var.disk_category
  # duration - (optional) is a type of string
  duration = var.duration
  # engine_type - (optional) is a type of string
  engine_type = var.engine_type
  # instance_alias - (optional) is a type of string
  instance_alias = var.instance_alias
  # instance_class - (required) is a type of string
  instance_class = var.instance_class
  # instance_storage - (required) is a type of string
  instance_storage = var.instance_storage
  # payment_type - (required) is a type of string
  payment_type = var.payment_type
  # vswitch_id - (required) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_tsdb_instance.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_tsdb_instance.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_tsdb_instance.this.zone_id
}

output "this" {
  value = alicloud_tsdb_instance.this
}
```

[top](#index)