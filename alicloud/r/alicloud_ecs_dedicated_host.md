# alicloud_ecs_dedicated_host

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
module "alicloud_ecs_dedicated_host" {
  source = "./modules/alicloud/r/alicloud_ecs_dedicated_host"

  # action_on_maintenance - (optional) is a type of string
  action_on_maintenance = null
  # auto_placement - (optional) is a type of string
  auto_placement = null
  # auto_release_time - (optional) is a type of string
  auto_release_time = null
  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # dedicated_host_name - (optional) is a type of string
  dedicated_host_name = null
  # dedicated_host_type - (required) is a type of string
  dedicated_host_type = null
  # description - (optional) is a type of string
  description = null
  # detail_fee - (optional) is a type of bool
  detail_fee = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # expired_time - (optional) is a type of string
  expired_time = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # sale_cycle - (optional) is a type of string
  sale_cycle = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_id - (optional) is a type of string
  zone_id = null

  network_attributes = [{
    slb_udp_timeout = null
    udp_timeout     = null
  }]

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action_on_maintenance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_placement" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_release_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dedicated_host_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dedicated_host_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "detail_fee" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "expired_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sale_cycle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_attributes" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      slb_udp_timeout = number
      udp_timeout     = number
    }
  ))
  default = []
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
resource "alicloud_ecs_dedicated_host" "this" {
  action_on_maintenance = var.action_on_maintenance
  auto_placement        = var.auto_placement
  auto_release_time     = var.auto_release_time
  auto_renew            = var.auto_renew
  auto_renew_period     = var.auto_renew_period
  dedicated_host_name   = var.dedicated_host_name
  dedicated_host_type   = var.dedicated_host_type
  description           = var.description
  detail_fee            = var.detail_fee
  dry_run               = var.dry_run
  expired_time          = var.expired_time
  payment_type          = var.payment_type
  resource_group_id     = var.resource_group_id
  sale_cycle            = var.sale_cycle
  tags                  = var.tags
  zone_id               = var.zone_id

  dynamic "network_attributes" {
    for_each = var.network_attributes
    content {
      slb_udp_timeout = network_attributes.value["slb_udp_timeout"]
      udp_timeout     = network_attributes.value["udp_timeout"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "expired_time" {
  description = "returns a string"
  value       = alicloud_ecs_dedicated_host.this.expired_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_ecs_dedicated_host.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_ecs_dedicated_host.this.resource_group_id
}

output "sale_cycle" {
  description = "returns a string"
  value       = alicloud_ecs_dedicated_host.this.sale_cycle
}

output "status" {
  description = "returns a string"
  value       = alicloud_ecs_dedicated_host.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_ecs_dedicated_host.this.zone_id
}

output "this" {
  value = alicloud_ecs_dedicated_host.this
}
```

[top](#index)