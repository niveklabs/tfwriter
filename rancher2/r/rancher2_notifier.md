# rancher2_notifier

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_notifier" {
  source = "./modules/rancher2/r/rancher2_notifier"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # send_resolved - (optional) is a type of bool
  send_resolved = null

  dingtalk_config = [{
    proxy_url = null
    secret    = null
    url       = null
  }]

  msteams_config = [{
    proxy_url = null
    url       = null
  }]

  pagerduty_config = [{
    proxy_url   = null
    service_key = null
  }]

  slack_config = [{
    default_recipient = null
    proxy_url         = null
    url               = null
  }]

  smtp_config = [{
    default_recipient = null
    host              = null
    password          = null
    port              = null
    sender            = null
    tls               = null
    username          = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  webhook_config = [{
    proxy_url = null
    url       = null
  }]

  wechat_config = [{
    agent             = null
    corp              = null
    default_recipient = null
    proxy_url         = null
    recipient_type    = null
    secret            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "cluster_id" {
  description = "(required) - Notifier cluster ID"
  type        = string
}

variable "description" {
  description = "(optional) - Notifier description"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Notifier name"
  type        = string
}

variable "send_resolved" {
  description = "(optional) - Notifier send resolved"
  type        = bool
  default     = null
}

variable "dingtalk_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      proxy_url = string
      secret    = string
      url       = string
    }
  ))
  default = []
}

variable "msteams_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      proxy_url = string
      url       = string
    }
  ))
  default = []
}

variable "pagerduty_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      proxy_url   = string
      service_key = string
    }
  ))
  default = []
}

variable "slack_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_recipient = string
      proxy_url         = string
      url               = string
    }
  ))
  default = []
}

variable "smtp_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_recipient = string
      host              = string
      password          = string
      port              = number
      sender            = string
      tls               = bool
      username          = string
    }
  ))
  default = []
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

variable "webhook_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      proxy_url = string
      url       = string
    }
  ))
  default = []
}

variable "wechat_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      agent             = string
      corp              = string
      default_recipient = string
      proxy_url         = string
      recipient_type    = string
      secret            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_notifier" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # send_resolved - (optional) is a type of bool
  send_resolved = var.send_resolved

  dynamic "dingtalk_config" {
    for_each = var.dingtalk_config
    content {
      # proxy_url - (optional) is a type of string
      proxy_url = dingtalk_config.value["proxy_url"]
      # secret - (optional) is a type of string
      secret = dingtalk_config.value["secret"]
      # url - (required) is a type of string
      url = dingtalk_config.value["url"]
    }
  }

  dynamic "msteams_config" {
    for_each = var.msteams_config
    content {
      # proxy_url - (optional) is a type of string
      proxy_url = msteams_config.value["proxy_url"]
      # url - (required) is a type of string
      url = msteams_config.value["url"]
    }
  }

  dynamic "pagerduty_config" {
    for_each = var.pagerduty_config
    content {
      # proxy_url - (optional) is a type of string
      proxy_url = pagerduty_config.value["proxy_url"]
      # service_key - (required) is a type of string
      service_key = pagerduty_config.value["service_key"]
    }
  }

  dynamic "slack_config" {
    for_each = var.slack_config
    content {
      # default_recipient - (required) is a type of string
      default_recipient = slack_config.value["default_recipient"]
      # proxy_url - (optional) is a type of string
      proxy_url = slack_config.value["proxy_url"]
      # url - (required) is a type of string
      url = slack_config.value["url"]
    }
  }

  dynamic "smtp_config" {
    for_each = var.smtp_config
    content {
      # default_recipient - (required) is a type of string
      default_recipient = smtp_config.value["default_recipient"]
      # host - (required) is a type of string
      host = smtp_config.value["host"]
      # password - (optional) is a type of string
      password = smtp_config.value["password"]
      # port - (required) is a type of number
      port = smtp_config.value["port"]
      # sender - (required) is a type of string
      sender = smtp_config.value["sender"]
      # tls - (optional) is a type of bool
      tls = smtp_config.value["tls"]
      # username - (optional) is a type of string
      username = smtp_config.value["username"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "webhook_config" {
    for_each = var.webhook_config
    content {
      # proxy_url - (optional) is a type of string
      proxy_url = webhook_config.value["proxy_url"]
      # url - (required) is a type of string
      url = webhook_config.value["url"]
    }
  }

  dynamic "wechat_config" {
    for_each = var.wechat_config
    content {
      # agent - (required) is a type of string
      agent = wechat_config.value["agent"]
      # corp - (required) is a type of string
      corp = wechat_config.value["corp"]
      # default_recipient - (required) is a type of string
      default_recipient = wechat_config.value["default_recipient"]
      # proxy_url - (optional) is a type of string
      proxy_url = wechat_config.value["proxy_url"]
      # recipient_type - (optional) is a type of string
      recipient_type = wechat_config.value["recipient_type"]
      # secret - (required) is a type of string
      secret = wechat_config.value["secret"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_notifier.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_notifier.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_notifier.this.labels
}

output "this" {
  value = rancher2_notifier.this
}
```

[top](#index)