# signalfx_org_token

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_org_token" {
  source = "./modules/signalfx/r/signalfx_org_token"

  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # name - (required) is a type of string
  name = null
  # notifications - (optional) is a type of list of string
  notifications = []

  dpm_limits = [{
    dpm_limit                  = null
    dpm_notification_threshold = null
  }]

  host_or_usage_limits = [{
    container_limit                         = null
    container_notification_threshold        = null
    custom_metrics_limit                    = null
    custom_metrics_notification_threshold   = null
    high_res_metrics_limit                  = null
    high_res_metrics_notification_threshold = null
    host_limit                              = null
    host_notification_threshold             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the token (Optional)"
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional) - Flag that controls enabling the token. If set to `true`, the token is disabled, and you can't use it for authentication. Defaults to `false`"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the token"
  type        = string
}

variable "notifications" {
  description = "(optional) - List of strings specifying where notifications will be sent when an incident occurs. See https://developers.signalfx.com/v2/docs/detector-model#notifications-models for more info"
  type        = list(string)
  default     = null
}

variable "dpm_limits" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      dpm_limit                  = number
      dpm_notification_threshold = number
    }
  ))
  default = []
}

variable "host_or_usage_limits" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      container_limit                         = number
      container_notification_threshold        = number
      custom_metrics_limit                    = number
      custom_metrics_notification_threshold   = number
      high_res_metrics_limit                  = number
      high_res_metrics_notification_threshold = number
      host_limit                              = number
      host_notification_threshold             = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_org_token" "this" {
  description   = var.description
  disabled      = var.disabled
  name          = var.name
  notifications = var.notifications

  dynamic "dpm_limits" {
    for_each = var.dpm_limits
    content {
      dpm_limit                  = dpm_limits.value["dpm_limit"]
      dpm_notification_threshold = dpm_limits.value["dpm_notification_threshold"]
    }
  }

  dynamic "host_or_usage_limits" {
    for_each = var.host_or_usage_limits
    content {
      container_limit                         = host_or_usage_limits.value["container_limit"]
      container_notification_threshold        = host_or_usage_limits.value["container_notification_threshold"]
      custom_metrics_limit                    = host_or_usage_limits.value["custom_metrics_limit"]
      custom_metrics_notification_threshold   = host_or_usage_limits.value["custom_metrics_notification_threshold"]
      high_res_metrics_limit                  = host_or_usage_limits.value["high_res_metrics_limit"]
      high_res_metrics_notification_threshold = host_or_usage_limits.value["high_res_metrics_notification_threshold"]
      host_limit                              = host_or_usage_limits.value["host_limit"]
      host_notification_threshold             = host_or_usage_limits.value["host_notification_threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_org_token.this.id
}

output "secret" {
  description = "returns a string"
  value       = signalfx_org_token.this.secret
  sensitive   = true
}

output "this" {
  value = signalfx_org_token.this
}
```

[top](#index)