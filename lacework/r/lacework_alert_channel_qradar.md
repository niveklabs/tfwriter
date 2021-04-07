# lacework_alert_channel_qradar

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
module "lacework_alert_channel_qradar" {
  source = "./modules/lacework/r/lacework_alert_channel_qradar"

  # communication_type - (optional) is a type of string
  communication_type = null
  # enabled - (optional) is a type of bool
  enabled = null
  # host_port - (optional) is a type of number
  host_port = null
  # host_url - (required) is a type of string
  host_url = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "communication_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "host_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "host_url" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_qradar" "this" {
  # communication_type - (optional) is a type of string
  communication_type = var.communication_type
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # host_port - (optional) is a type of number
  host_port = var.host_port
  # host_url - (required) is a type of string
  host_url = var.host_url
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_qradar.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_qradar.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_qradar.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_qradar.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_qradar.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_qradar.this.type_name
}

output "this" {
  value = lacework_alert_channel_qradar.this
}
```

[top](#index)