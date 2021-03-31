# circonus_contact_group

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.12.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_contact_group" {
  source = "./modules/circonus/r/circonus_contact_group"

  # aggregation_window - (optional) is a type of string
  aggregation_window = null
  # always_send_clear - (optional) is a type of bool
  always_send_clear = null
  # group_type - (optional) is a type of string
  group_type = null
  # long_message - (optional) is a type of string
  long_message = null
  # long_subject - (optional) is a type of string
  long_subject = null
  # long_summary - (optional) is a type of string
  long_summary = null
  # name - (required) is a type of string
  name = null
  # short_message - (optional) is a type of string
  short_message = null
  # short_summary - (optional) is a type of string
  short_summary = null
  # tags - (optional) is a type of set of string
  tags = []

  alert_option = [{
    escalate_after = null
    escalate_to    = null
    reminder       = null
    severity       = null
  }]

  email = [{
    address = null
    user    = null
  }]

  http = [{
    address = null
    format  = null
    method  = null
  }]

  pager_duty = [{
    account                = null
    contact_group_fallback = null
    service_key            = null
    webhook_url            = null
  }]

  slack = [{
    buttons                = null
    channel                = null
    contact_group_fallback = null
    team                   = null
    username               = null
  }]

  sms = [{
    address = null
    user    = null
  }]

  victorops = [{
    api_key                = null
    contact_group_fallback = null
    critical               = null
    info                   = null
    team                   = null
    warning                = null
  }]

  xmpp = [{
    address = null
    user    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aggregation_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "always_send_clear" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "long_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "long_subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "long_summary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "short_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "short_summary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "alert_option" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      escalate_after = string
      escalate_to    = string
      reminder       = string
      severity       = number
    }
  ))
  default = []
}

variable "email" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address = string
      user    = string
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address = string
      format  = string
      method  = string
    }
  ))
  default = []
}

variable "pager_duty" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      account                = string
      contact_group_fallback = string
      service_key            = string
      webhook_url            = string
    }
  ))
  default = []
}

variable "slack" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      buttons                = bool
      channel                = string
      contact_group_fallback = string
      team                   = string
      username               = string
    }
  ))
  default = []
}

variable "sms" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address = string
      user    = string
    }
  ))
  default = []
}

variable "victorops" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      api_key                = string
      contact_group_fallback = string
      critical               = number
      info                   = number
      team                   = string
      warning                = number
    }
  ))
  default = []
}

variable "xmpp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address = string
      user    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "circonus_contact_group" "this" {
  aggregation_window = var.aggregation_window
  always_send_clear  = var.always_send_clear
  group_type         = var.group_type
  long_message       = var.long_message
  long_subject       = var.long_subject
  long_summary       = var.long_summary
  name               = var.name
  short_message      = var.short_message
  short_summary      = var.short_summary
  tags               = var.tags

  dynamic "alert_option" {
    for_each = var.alert_option
    content {
      escalate_after = alert_option.value["escalate_after"]
      escalate_to    = alert_option.value["escalate_to"]
      reminder       = alert_option.value["reminder"]
      severity       = alert_option.value["severity"]
    }
  }

  dynamic "email" {
    for_each = var.email
    content {
      address = email.value["address"]
      user    = email.value["user"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      address = http.value["address"]
      format  = http.value["format"]
      method  = http.value["method"]
    }
  }

  dynamic "pager_duty" {
    for_each = var.pager_duty
    content {
      account                = pager_duty.value["account"]
      contact_group_fallback = pager_duty.value["contact_group_fallback"]
      service_key            = pager_duty.value["service_key"]
      webhook_url            = pager_duty.value["webhook_url"]
    }
  }

  dynamic "slack" {
    for_each = var.slack
    content {
      buttons                = slack.value["buttons"]
      channel                = slack.value["channel"]
      contact_group_fallback = slack.value["contact_group_fallback"]
      team                   = slack.value["team"]
      username               = slack.value["username"]
    }
  }

  dynamic "sms" {
    for_each = var.sms
    content {
      address = sms.value["address"]
      user    = sms.value["user"]
    }
  }

  dynamic "victorops" {
    for_each = var.victorops
    content {
      api_key                = victorops.value["api_key"]
      contact_group_fallback = victorops.value["contact_group_fallback"]
      critical               = victorops.value["critical"]
      info                   = victorops.value["info"]
      team                   = victorops.value["team"]
      warning                = victorops.value["warning"]
    }
  }

  dynamic "xmpp" {
    for_each = var.xmpp
    content {
      address = xmpp.value["address"]
      user    = xmpp.value["user"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = circonus_contact_group.this.id
}

output "last_modified" {
  description = "returns a number"
  value       = circonus_contact_group.this.last_modified
}

output "last_modified_by" {
  description = "returns a string"
  value       = circonus_contact_group.this.last_modified_by
}

output "this" {
  value = circonus_contact_group.this
}
```

[top](#index)