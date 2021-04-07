# alicloud_quotas_application_info

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
module "alicloud_quotas_application_info" {
  source = "./modules/alicloud/r/alicloud_quotas_application_info"

  # audit_mode - (optional) is a type of string
  audit_mode = null
  # desire_value - (required) is a type of number
  desire_value = null
  # notice_type - (optional) is a type of number
  notice_type = null
  # product_code - (required) is a type of string
  product_code = null
  # quota_action_code - (required) is a type of string
  quota_action_code = null
  # quota_category - (optional) is a type of string
  quota_category = null
  # reason - (required) is a type of string
  reason = null

  dimensions = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "audit_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desire_value" {
  description = "(required)"
  type        = number
}

variable "notice_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "product_code" {
  description = "(required)"
  type        = string
}

variable "quota_action_code" {
  description = "(required)"
  type        = string
}

variable "quota_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reason" {
  description = "(required)"
  type        = string
}

variable "dimensions" {
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
resource "alicloud_quotas_application_info" "this" {
  # audit_mode - (optional) is a type of string
  audit_mode = var.audit_mode
  # desire_value - (required) is a type of number
  desire_value = var.desire_value
  # notice_type - (optional) is a type of number
  notice_type = var.notice_type
  # product_code - (required) is a type of string
  product_code = var.product_code
  # quota_action_code - (required) is a type of string
  quota_action_code = var.quota_action_code
  # quota_category - (optional) is a type of string
  quota_category = var.quota_category
  # reason - (required) is a type of string
  reason = var.reason

  dynamic "dimensions" {
    for_each = var.dimensions
    content {
      # key - (optional) is a type of string
      key = dimensions.value["key"]
      # value - (optional) is a type of string
      value = dimensions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "approve_value" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.approve_value
}

output "audit_reason" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.audit_reason
}

output "effective_time" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.effective_time
}

output "expire_time" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.expire_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.id
}

output "quota_description" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.quota_description
}

output "quota_name" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.quota_name
}

output "quota_unit" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.quota_unit
}

output "status" {
  description = "returns a string"
  value       = alicloud_quotas_application_info.this.status
}

output "this" {
  value = alicloud_quotas_application_info.this
}
```

[top](#index)