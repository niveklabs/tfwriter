# alicloud_quotas_quota_alarms

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_quotas_quota_alarms" {
  source = "./modules/alicloud/d/alicloud_quotas_quota_alarms"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # product_code - (optional) is a type of string
  product_code = null
  # quota_action_code - (optional) is a type of string
  quota_action_code = null
  # quota_alarm_name - (optional) is a type of string
  quota_alarm_name = null

  quota_dimensions = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_action_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_alarm_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_dimensions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

### Datasource

```terraform
data "alicloud_quotas_quota_alarms" "this" {
  # enable_details - (optional) is a type of bool
  enable_details = var.enable_details
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # product_code - (optional) is a type of string
  product_code = var.product_code
  # quota_action_code - (optional) is a type of string
  quota_action_code = var.quota_action_code
  # quota_alarm_name - (optional) is a type of string
  quota_alarm_name = var.quota_alarm_name

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
output "alarms" {
  description = "returns a list of object"
  value       = data.alicloud_quotas_quota_alarms.this.alarms
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_quotas_quota_alarms.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_quotas_quota_alarms.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_quotas_quota_alarms.this.names
}

output "this" {
  value = alicloud_quotas_quota_alarms.this
}
```

[top](#index)