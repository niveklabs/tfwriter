# alicloud_cms_alarm_contact_group

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
module "alicloud_cms_alarm_contact_group" {
  source = "./modules/alicloud/r/alicloud_cms_alarm_contact_group"

  # alarm_contact_group_name - (required) is a type of string
  alarm_contact_group_name = null
  # contacts - (optional) is a type of set of string
  contacts = []
  # describe - (optional) is a type of string
  describe = null
  # enable_subscribed - (optional) is a type of bool
  enable_subscribed = null
}
```

[top](#index)

### Variables

```terraform
variable "alarm_contact_group_name" {
  description = "(required)"
  type        = string
}

variable "contacts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "describe" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_subscribed" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cms_alarm_contact_group" "this" {
  alarm_contact_group_name = var.alarm_contact_group_name
  contacts                 = var.contacts
  describe                 = var.describe
  enable_subscribed        = var.enable_subscribed
}
```

[top](#index)

### Outputs

```terraform
output "enable_subscribed" {
  description = "returns a bool"
  value       = alicloud_cms_alarm_contact_group.this.enable_subscribed
}

output "id" {
  description = "returns a string"
  value       = alicloud_cms_alarm_contact_group.this.id
}

output "this" {
  value = alicloud_cms_alarm_contact_group.this
}
```

[top](#index)