# lacework_alert_channel_splunk

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
module "lacework_alert_channel_splunk" {
  source = "./modules/lacework/r/lacework_alert_channel_splunk"

  # channel - (optional) is a type of string
  channel = null
  # enabled - (optional) is a type of bool
  enabled = null
  # hec_token - (required) is a type of string
  hec_token = null
  # host - (required) is a type of string
  host = null
  # name - (required) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # ssl - (optional) is a type of bool
  ssl = null

  event_data = [{
    index  = null
    source = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hec_token" {
  description = "(required)"
  type        = string
}

variable "host" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "ssl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "event_data" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      index  = string
      source = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "lacework_alert_channel_splunk" "this" {
  channel   = var.channel
  enabled   = var.enabled
  hec_token = var.hec_token
  host      = var.host
  name      = var.name
  port      = var.port
  ssl       = var.ssl

  dynamic "event_data" {
    for_each = var.event_data
    content {
      index  = event_data.value["index"]
      source = event_data.value["source"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_alert_channel_splunk.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_alert_channel_splunk.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_alert_channel_splunk.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_alert_channel_splunk.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_alert_channel_splunk.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_alert_channel_splunk.this.type_name
}

output "this" {
  value = lacework_alert_channel_splunk.this
}
```

[top](#index)