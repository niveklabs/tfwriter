# alicloud_cms_alarm_contact

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
module "alicloud_cms_alarm_contact" {
  source = "./modules/alicloud/r/alicloud_cms_alarm_contact"

  # alarm_contact_name - (required) is a type of string
  alarm_contact_name = null
  # channels_aliim - (optional) is a type of string
  channels_aliim = null
  # channels_ding_web_hook - (optional) is a type of string
  channels_ding_web_hook = null
  # channels_mail - (optional) is a type of string
  channels_mail = null
  # channels_sms - (optional) is a type of string
  channels_sms = null
  # describe - (required) is a type of string
  describe = null
  # lang - (optional) is a type of string
  lang = null
}
```

[top](#index)

### Variables

```terraform
variable "alarm_contact_name" {
  description = "(required)"
  type        = string
}

variable "channels_aliim" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "channels_ding_web_hook" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "channels_mail" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "channels_sms" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "describe" {
  description = "(required)"
  type        = string
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cms_alarm_contact" "this" {
  alarm_contact_name     = var.alarm_contact_name
  channels_aliim         = var.channels_aliim
  channels_ding_web_hook = var.channels_ding_web_hook
  channels_mail          = var.channels_mail
  channels_sms           = var.channels_sms
  describe               = var.describe
  lang                   = var.lang
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cms_alarm_contact.this.id
}

output "this" {
  value = alicloud_cms_alarm_contact.this
}
```

[top](#index)