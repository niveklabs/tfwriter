# alicloud_cen_vbr_health_check

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
module "alicloud_cen_vbr_health_check" {
  source = "./modules/alicloud/r/alicloud_cen_vbr_health_check"

  # cen_id - (required) is a type of string
  cen_id = null
  # health_check_interval - (optional) is a type of number
  health_check_interval = null
  # health_check_source_ip - (optional) is a type of string
  health_check_source_ip = null
  # health_check_target_ip - (required) is a type of string
  health_check_target_ip = null
  # healthy_threshold - (optional) is a type of number
  healthy_threshold = null
  # vbr_instance_id - (required) is a type of string
  vbr_instance_id = null
  # vbr_instance_owner_id - (optional) is a type of number
  vbr_instance_owner_id = null
  # vbr_instance_region_id - (required) is a type of string
  vbr_instance_region_id = null

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
variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "health_check_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_target_ip" {
  description = "(required)"
  type        = string
}

variable "healthy_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vbr_instance_id" {
  description = "(required)"
  type        = string
}

variable "vbr_instance_owner_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vbr_instance_region_id" {
  description = "(required)"
  type        = string
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
resource "alicloud_cen_vbr_health_check" "this" {
  cen_id                 = var.cen_id
  health_check_interval  = var.health_check_interval
  health_check_source_ip = var.health_check_source_ip
  health_check_target_ip = var.health_check_target_ip
  healthy_threshold      = var.healthy_threshold
  vbr_instance_id        = var.vbr_instance_id
  vbr_instance_owner_id  = var.vbr_instance_owner_id
  vbr_instance_region_id = var.vbr_instance_region_id

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
output "id" {
  description = "returns a string"
  value       = alicloud_cen_vbr_health_check.this.id
}

output "this" {
  value = alicloud_cen_vbr_health_check.this
}
```

[top](#index)