# alicloud_quotas_quota_alarm

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
module "alicloud_quotas_quota_alarm" {
  source = "./modules/alicloud/r/alicloud_quotas_quota_alarm"

  # product_code - (required) is a type of string
  product_code = null
  # quota_action_code - (required) is a type of string
  quota_action_code = null
  # quota_alarm_name - (required) is a type of string
  quota_alarm_name = null
  # threshold - (optional) is a type of number
  threshold = null
  # threshold_percent - (optional) is a type of number
  threshold_percent = null
  # web_hook - (optional) is a type of string
  web_hook = null

  quota_dimensions = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "product_code" {
  description = "(required)"
  type        = string
}

variable "quota_action_code" {
  description = "(required)"
  type        = string
}

variable "quota_alarm_name" {
  description = "(required)"
  type        = string
}

variable "threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "threshold_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "web_hook" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_dimensions" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_quotas_quota_alarm" "this" {
  # product_code - (required) is a type of string
  product_code = var.product_code
  # quota_action_code - (required) is a type of string
  quota_action_code = var.quota_action_code
  # quota_alarm_name - (required) is a type of string
  quota_alarm_name = var.quota_alarm_name
  # threshold - (optional) is a type of number
  threshold = var.threshold
  # threshold_percent - (optional) is a type of number
  threshold_percent = var.threshold_percent
  # web_hook - (optional) is a type of string
  web_hook = var.web_hook

  dynamic "quota_dimensions" {
    for_each = var.quota_dimensions
    content {
      # key - (optional) is a type of string
      key = quota_dimensions.value["key"]
      # value - (optional) is a type of string
      value = quota_dimensions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_quotas_quota_alarm.this.id
}

output "this" {
  value = alicloud_quotas_quota_alarm.this
}
```

[top](#index)