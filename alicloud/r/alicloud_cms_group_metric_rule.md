# alicloud_cms_group_metric_rule

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
module "alicloud_cms_group_metric_rule" {
  source = "./modules/alicloud/r/alicloud_cms_group_metric_rule"

  # category - (required) is a type of string
  category = null
  # contact_groups - (optional) is a type of string
  contact_groups = null
  # dimensions - (optional) is a type of string
  dimensions = null
  # effective_interval - (optional) is a type of string
  effective_interval = null
  # email_subject - (optional) is a type of string
  email_subject = null
  # group_id - (required) is a type of string
  group_id = null
  # group_metric_rule_name - (required) is a type of string
  group_metric_rule_name = null
  # interval - (optional) is a type of string
  interval = null
  # metric_name - (required) is a type of string
  metric_name = null
  # namespace - (required) is a type of string
  namespace = null
  # no_effective_interval - (optional) is a type of string
  no_effective_interval = null
  # period - (optional) is a type of number
  period = null
  # rule_id - (required) is a type of string
  rule_id = null
  # silence_time - (optional) is a type of number
  silence_time = null
  # webhook - (optional) is a type of string
  webhook = null

  escalations = [{
    critical = [{
      comparison_operator = null
      statistics          = null
      threshold           = null
      times               = null
    }]
    info = [{
      comparison_operator = null
      statistics          = null
      threshold           = null
      times               = null
    }]
    warn = [{
      comparison_operator = null
      statistics          = null
      threshold           = null
      times               = null
    }]
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
variable "category" {
  description = "(required)"
  type        = string
}

variable "contact_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dimensions" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "effective_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "group_metric_rule_name" {
  description = "(required)"
  type        = string
}

variable "interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metric_name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "no_effective_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rule_id" {
  description = "(required)"
  type        = string
}

variable "silence_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "webhook" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "escalations" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      critical = set(object(
        {
          comparison_operator = string
          statistics          = string
          threshold           = string
          times               = number
        }
      ))
      info = set(object(
        {
          comparison_operator = string
          statistics          = string
          threshold           = string
          times               = number
        }
      ))
      warn = set(object(
        {
          comparison_operator = string
          statistics          = string
          threshold           = string
          times               = number
        }
      ))
    }
  ))
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
resource "alicloud_cms_group_metric_rule" "this" {
  # category - (required) is a type of string
  category = var.category
  # contact_groups - (optional) is a type of string
  contact_groups = var.contact_groups
  # dimensions - (optional) is a type of string
  dimensions = var.dimensions
  # effective_interval - (optional) is a type of string
  effective_interval = var.effective_interval
  # email_subject - (optional) is a type of string
  email_subject = var.email_subject
  # group_id - (required) is a type of string
  group_id = var.group_id
  # group_metric_rule_name - (required) is a type of string
  group_metric_rule_name = var.group_metric_rule_name
  # interval - (optional) is a type of string
  interval = var.interval
  # metric_name - (required) is a type of string
  metric_name = var.metric_name
  # namespace - (required) is a type of string
  namespace = var.namespace
  # no_effective_interval - (optional) is a type of string
  no_effective_interval = var.no_effective_interval
  # period - (optional) is a type of number
  period = var.period
  # rule_id - (required) is a type of string
  rule_id = var.rule_id
  # silence_time - (optional) is a type of number
  silence_time = var.silence_time
  # webhook - (optional) is a type of string
  webhook = var.webhook

  dynamic "escalations" {
    for_each = var.escalations
    content {

      dynamic "critical" {
        for_each = escalations.value.critical
        content {
          # comparison_operator - (optional) is a type of string
          comparison_operator = critical.value["comparison_operator"]
          # statistics - (optional) is a type of string
          statistics = critical.value["statistics"]
          # threshold - (optional) is a type of string
          threshold = critical.value["threshold"]
          # times - (optional) is a type of number
          times = critical.value["times"]
        }
      }

      dynamic "info" {
        for_each = escalations.value.info
        content {
          # comparison_operator - (optional) is a type of string
          comparison_operator = info.value["comparison_operator"]
          # statistics - (optional) is a type of string
          statistics = info.value["statistics"]
          # threshold - (optional) is a type of string
          threshold = info.value["threshold"]
          # times - (optional) is a type of number
          times = info.value["times"]
        }
      }

      dynamic "warn" {
        for_each = escalations.value.warn
        content {
          # comparison_operator - (optional) is a type of string
          comparison_operator = warn.value["comparison_operator"]
          # statistics - (optional) is a type of string
          statistics = warn.value["statistics"]
          # threshold - (optional) is a type of string
          threshold = warn.value["threshold"]
          # times - (optional) is a type of number
          times = warn.value["times"]
        }
      }

    }
  }

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
output "contact_groups" {
  description = "returns a string"
  value       = alicloud_cms_group_metric_rule.this.contact_groups
}

output "dimensions" {
  description = "returns a string"
  value       = alicloud_cms_group_metric_rule.this.dimensions
}

output "email_subject" {
  description = "returns a string"
  value       = alicloud_cms_group_metric_rule.this.email_subject
}

output "id" {
  description = "returns a string"
  value       = alicloud_cms_group_metric_rule.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_cms_group_metric_rule.this.status
}

output "this" {
  value = alicloud_cms_group_metric_rule.this
}
```

[top](#index)