# alicloud_fnf_schedule

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
module "alicloud_fnf_schedule" {
  source = "./modules/alicloud/r/alicloud_fnf_schedule"

  # cron_expression - (required) is a type of string
  cron_expression = null
  # description - (optional) is a type of string
  description = null
  # enable - (optional) is a type of bool
  enable = null
  # flow_name - (required) is a type of string
  flow_name = null
  # payload - (optional) is a type of string
  payload = null
  # schedule_name - (required) is a type of string
  schedule_name = null

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
variable "cron_expression" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "flow_name" {
  description = "(required)"
  type        = string
}

variable "payload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_name" {
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
resource "alicloud_fnf_schedule" "this" {
  cron_expression = var.cron_expression
  description     = var.description
  enable          = var.enable
  flow_name       = var.flow_name
  payload         = var.payload
  schedule_name   = var.schedule_name

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
  value       = alicloud_fnf_schedule.this.id
}

output "last_modified_time" {
  description = "returns a string"
  value       = alicloud_fnf_schedule.this.last_modified_time
}

output "schedule_id" {
  description = "returns a string"
  value       = alicloud_fnf_schedule.this.schedule_id
}

output "this" {
  value = alicloud_fnf_schedule.this
}
```

[top](#index)