# alicloud_config_delivery_channel

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_config_delivery_channel" {
  source = "./modules/alicloud/r/alicloud_config_delivery_channel"

  # delivery_channel_assume_role_arn - (required) is a type of string
  delivery_channel_assume_role_arn = null
  # delivery_channel_condition - (optional) is a type of string
  delivery_channel_condition = null
  # delivery_channel_name - (optional) is a type of string
  delivery_channel_name = null
  # delivery_channel_target_arn - (required) is a type of string
  delivery_channel_target_arn = null
  # delivery_channel_type - (required) is a type of string
  delivery_channel_type = null
  # description - (optional) is a type of string
  description = null
  # status - (optional) is a type of number
  status = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delivery_channel_assume_role_arn" {
  description = "(required)"
  type        = string
}

variable "delivery_channel_condition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delivery_channel_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delivery_channel_target_arn" {
  description = "(required)"
  type        = string
}

variable "delivery_channel_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = number
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
resource "alicloud_config_delivery_channel" "this" {
  delivery_channel_assume_role_arn = var.delivery_channel_assume_role_arn
  delivery_channel_condition       = var.delivery_channel_condition
  delivery_channel_name            = var.delivery_channel_name
  delivery_channel_target_arn      = var.delivery_channel_target_arn
  delivery_channel_type            = var.delivery_channel_type
  description                      = var.description
  status                           = var.status

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
output "delivery_channel_condition" {
  description = "returns a string"
  value       = alicloud_config_delivery_channel.this.delivery_channel_condition
}

output "delivery_channel_name" {
  description = "returns a string"
  value       = alicloud_config_delivery_channel.this.delivery_channel_name
}

output "description" {
  description = "returns a string"
  value       = alicloud_config_delivery_channel.this.description
}

output "id" {
  description = "returns a string"
  value       = alicloud_config_delivery_channel.this.id
}

output "status" {
  description = "returns a number"
  value       = alicloud_config_delivery_channel.this.status
}

output "this" {
  value = alicloud_config_delivery_channel.this
}
```

[top](#index)