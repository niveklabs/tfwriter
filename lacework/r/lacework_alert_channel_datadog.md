# lacework_alert_channel_datadog

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_alert_channel_datadog" {
  source = "./modules/lacework/r/lacework_alert_channel_datadog"

  # api_key - (required) is a type of string
  api_key = null
  # datadog_service - (optional) is a type of string
  datadog_service = null
  # datadog_site - (optional) is a type of string
  datadog_site = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key" {
  description = "(required)"
  type        = string
}

variable "datadog_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datadog_site" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_datadog" "this" {
  api_key         = var.api_key
  datadog_service = var.datadog_service
  datadog_site    = var.datadog_site
  enabled         = var.enabled
  name            = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_datadog.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_datadog.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_datadog.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_datadog.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_datadog.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_datadog.this.type_name
}

output "this" {
  value = lacework_alert_channel_datadog.this
}
```

[top](#index)