# prismacloud_enterprise_settings

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_enterprise_settings" {
  source = "./modules/prismacloud/r/prismacloud_enterprise_settings"

  # anomaly_alert_disposition - (optional) is a type of string
  anomaly_alert_disposition = null
  # anomaly_training_model_threshold - (optional) is a type of string
  anomaly_training_model_threshold = null
  # apply_default_policies_enabled - (optional) is a type of bool
  apply_default_policies_enabled = null
  # default_policies_enabled - (optional) is a type of map of bool
  default_policies_enabled = {}
  # require_alert_dismissal_note - (optional) is a type of bool
  require_alert_dismissal_note = null
  # session_timeout - (optional) is a type of number
  session_timeout = null
  # user_attribution_in_notification - (optional) is a type of bool
  user_attribution_in_notification = null
}
```

[top](#index)

### Variables

```terraform
variable "anomaly_alert_disposition" {
  description = "(optional) - Anomaly alert disposition"
  type        = string
  default     = null
}

variable "anomaly_training_model_threshold" {
  description = "(optional) - Anomaly training model threshold"
  type        = string
  default     = null
}

variable "apply_default_policies_enabled" {
  description = "(optional) - Apply default policies enabled"
  type        = bool
  default     = null
}

variable "default_policies_enabled" {
  description = "(optional) - Default policies enabled"
  type        = map(bool)
  default     = null
}

variable "require_alert_dismissal_note" {
  description = "(optional) - Require alert dismissal note"
  type        = bool
  default     = null
}

variable "session_timeout" {
  description = "(optional) - Browser session timeout"
  type        = number
  default     = null
}

variable "user_attribution_in_notification" {
  description = "(optional) - User attribution in notification"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_enterprise_settings" "this" {
  anomaly_alert_disposition        = var.anomaly_alert_disposition
  anomaly_training_model_threshold = var.anomaly_training_model_threshold
  apply_default_policies_enabled   = var.apply_default_policies_enabled
  default_policies_enabled         = var.default_policies_enabled
  require_alert_dismissal_note     = var.require_alert_dismissal_note
  session_timeout                  = var.session_timeout
  user_attribution_in_notification = var.user_attribution_in_notification
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = prismacloud_enterprise_settings.this.id
}

output "this" {
  value = prismacloud_enterprise_settings.this
}
```

[top](#index)