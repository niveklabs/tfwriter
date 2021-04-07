# rancher2_notifier

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/rancher2/d/rancher2_notifier"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null

  dingtalk_config = [{
    proxy_url = null
    secret    = null
    url       = null
  }]

  msteams_config = [{
    proxy_url = null
    url       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - Notifier cluster ID"
  type        = string
}

variable "name" {
  description = "(required) - Notifier name"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "rancher2_notifier" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # name - (required) is a type of string
  name = var.name

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

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_notifier.this.annotations
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_notifier.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_notifier.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_notifier.this.labels
}

output "pagerduty_config" {
  description = "returns a list of object"
  value       = data.rancher2_notifier.this.pagerduty_config
}

output "slack_config" {
  description = "returns a list of object"
  value       = data.rancher2_notifier.this.slack_config
}

output "smtp_config" {
  description = "returns a list of object"
  value       = data.rancher2_notifier.this.smtp_config
}

output "webhook_config" {
  description = "returns a list of object"
  value       = data.rancher2_notifier.this.webhook_config
}

output "wechat_config" {
  description = "returns a list of object"
  value       = data.rancher2_notifier.this.wechat_config
}

output "this" {
  value = rancher2_notifier.this
}
```

[top](#index)